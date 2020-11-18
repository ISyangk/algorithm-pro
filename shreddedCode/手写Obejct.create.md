## 手写一个Object.create
### 理解点
1.Object.create的作用是使用现有的对象来为了新创建的对象提供原型对象
2.需理解原型链
3.手写instanceof中有介绍原型链所涉及的知识点

### 代码
```js
Object.prototype.createObj = function(O, prototype) {
    const obj = {};
    Object.setPrototypeof(obj, O);
    return obj;
}
```

ps: 需理解Object.setPortotypeof（A,B）的作用，该api的作用是将B对象设置为A对象的原型。