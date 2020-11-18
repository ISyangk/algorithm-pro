## 手写instanceof
### 考察点
#### 考察对原型链的理解
1.理解隐式原型（__proto__）、显式原型（prototype）以及constructor
2.__proto__与construcotr只存在于对象上
3.prototype是函数特有的
4.由于函数式特殊的对象，所以也具备__proto__和constructor

#### __proto__的作用
通常获取对象属性时，如果未获取到，则会根据__proto__去向上查找，直到原型对象为null为止，该连接对象的过程形成了我们所谓的原型链。

#### prototype的作用
函数的原型对象，从一个函数指向一个对象。主要是让该函数所实例化的对象们都可以找到共有的属性和方法。

#### constructor的作用
从一个对象指向一个函数，所有函数的构造函数最终都指向Function

#### 实现instanceof
```js
// 实现等同于instanceof功能的代码，instanceof用于检测构造函数的prototype属性是否存在于某个实例化对象的原型链上
//eg: A instanceof B ,指的是的B的原型对象是否存在于A的原型链上
// 如果需要排除基础类型的影响，则另外补充相应代码
function myInstanceof(left, right) {
    let leftValue = left.__proto__;
    const rightProto = right.prototype;
    while(true) {
        if (leftValue === null) {
            return false;
        }
        if (leftValue === rightProto) {
            return true;
        }
        leftValue = leftValue.__proto__;
    }
}
```
