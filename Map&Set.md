## WeakMap

### Specification
ECMAScript 2015 (6th Edition, ECMA-262)

### Why WeakMap
在 JavaScript 里，map API 可以通过在其四个 API 方法中共用两个数组(一个存放键,一个存放值)来实现。给该 map 设置值时会同时将键和值推到这两个数组的末尾。从而使得键和值的索引在两个数组中相对应。当从该 map 取值的时候，需要遍历所有的键，然后使用此索引从存储值的数组中检索出相应的值。

但这样的实现会有两个很大的缺点，首先是O(n)的时间复杂度(n是键值对的个数)。另外一个则可能会导致内存泄漏:在这种自己实现的 WeakMap 中,存放键的数组中的每个索引将会保持对所引用对象的引用,阻止他们被当作垃圾回收.

而在原生的WeakMap中,每个键对自己所引用对象的引用是 "弱引用", 这意味着,如果没有其他引用和该键引用同一个对象,这个对象将会被当作垃圾回收。原生 WeakMap 的结构是特殊且有效的，其用于映射的 key 只有在其没有被回收时才是有效的。

正由于这样的弱引用，WeakMap 的 key 是不可枚举的 (没有方法能给出所有的 key)。如果key 是可枚举的话，其列表将会受垃圾回收机制的影响，从而得到不确定的结果. 因此,如果你想要这种类型对象的 key 值的列表，你应该使用 Map。

### 个人学习经历
Map和Set这两个数据类型之前就有了解，但一直没在项目中实际应用过，了解止于概念。最近查看网上实现js深拷贝的文章时，其中一种方法用了WeakMap，所以进一步学习一下。

## Reference
1.[带键的集合](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Keyed_collections#WeakMap_object)

2.[WeakMap](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)

3.[深入 js 深拷贝对象](https://www.jianshu.com/p/b08bc61714c7)

4.[JavaScript 如何完整实现深度Clone对象](https://www.zhihu.com/question/47746441)
