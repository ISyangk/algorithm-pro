## 手写一个new方法
### 主要考察原型链
手写instanceof中有介绍原型链所涉及的知识点

```js
function myNew(fn, ...args) {
    const obj = {};
    obj.__proto__ = fn.prototype;
    const result = fn.apply(obj, args);
    return (result instanceof Object) ? result : obj;
}
```