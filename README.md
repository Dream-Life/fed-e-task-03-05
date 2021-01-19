# fed-e-task-03-05
大前端进阶 - 阶段三 - 模块五



##### 1、Vue 3.0 性能提升主要是通过哪几方面体现的？

 1. 响应式系统升级，改成proxy

 2. 编译优化，diff的优化 - Fragment；静态提升；Patch flag；缓存事件处理

 3. 源码体积优化，按需加载，tree-shaking

    

##### 2、Vue 3.0 所采用的 Composition Api 与 Vue 2.x使用的Options Api 有什么区别？

​	Composition Api 将一个个功能分成函数，相比于Options Api更容易分辨，查找和维护，也增加了功能的复用；

​	Composition Api将功能函数一个个按需加载，更灵活的组织组件的逻辑；



##### 3、Proxy 相对于 Object.defineProperty 有哪些优点？

	1. Proxy可以监听动态新增的属性
 	2. Proxy可以监听删除的属性
 	3. Proxy可以监听数组的索引和length属性



##### 4、Vue 3.0 在编译方面有哪些优化？

​	diff的时候只对比动态节点内容

​	 方法：Fragment；静态提升；Patch flag；缓存事件处理



##### 5、Vue.js 3.0 响应式系统的实现原理？

​	通过proxy可以实现对象属性的监听，在proxy监听对象的get获取时会收集依赖，将effect函数放入new Set()，new Set()放入new Map()和对象的属性名对应，最后是new Map()和new WeakMap()的对象对应起来，这样就完成了依赖收集；之后在set和deleteProperty时触发更新，执行effect函数；这样就能实现数据的响应式。