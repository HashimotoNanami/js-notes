## Reflect

### Specification
ECMAScript 2015 (6th Edition, ECMA-262)

### notes
Reflect.ownKeys 方法返回一个由目标对象自身的属性键组成的数组。它的返回值等同于Object.getOwnPropertyNames(target).concat(Object.getOwnPropertySymbols(target))

### 个人学习经历
最近查看网上实现js深拷贝的文章时，在探索方法里提到了Reflect，学习一下。

## Reference
1.[深入 js 深拷贝对象](https://www.jianshu.com/p/b08bc61714c7)

2.[Reflect](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect)