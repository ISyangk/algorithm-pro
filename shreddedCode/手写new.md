## 手写一个new方法
```js
function myNew(fn, ...args) {
    const obj = {};
    obj.__proto__ = fn.prototype;
    const result = fn.apply(obj, args);
    return (result instanceof Object) ? result : obj;
}
```