#### 1、Vue 3.0 性能提升主要是通过哪几方面体现的？
>答：
>   - 性能提升
>       - 响应式系统升级
>       - 编译优化
>       - 源码体积的优化

>   - 响应式系统升级
>       - Vue.js 2.x 中响应式系统的核心 defineProperty
>       - Vue.js 3.0 中使用 Proxy 对象重写响应式系统
>           - 可以监听动态新增的属性
>           - 可以监听删除的属性
>           - 可以监听数组的索引和 length 属性
>   - 编译优化
>       - Vue.js2.x中通过标记静态根节点，优化diff的过程
>       - Vue.js3.0中标记和提升所有的静态根节点，diff的时候只需要对比动态节点内容
>           - Fragments（升级vetur插件）
>           - 静态提升
>           - Patchflag
>           - 缓存事件处理函数
>   - 优化打包体积
>       - Vue.js3.0中移除了一些不常用的API
        - 例如：inline-template、filter等
>       - Tree-shaking

#### 2、Vue 3.0 所采用的 Composition Api 与 Vue 2.x使用的Options Api 有什么区别？
>答：
>   - Options API
>       - 包含一个描述组件选项（data、methods、props等）的对象
>       - Oprions API 开发复杂组件，同一个功能逻辑的代码被拆分到不同选项
>   - Composition API
>       - Vue.js3.0新增的一组API
>       - 一组基于函数的API
>       - 可以更灵活的组织组件的逻辑
#### 3、Proxy 相对于 Object.defineProperty 有哪些优点？
>答：
>   - 可以监听动态新增的属性
>   - 可以监听删除的属性
>   - 可以监听数组的索引和 length 属性
>   - 可以劫持整个对象，并返回一个新对象
>   - 有13种劫持操作

#### 4、Vue 3.0 在编译方面有哪些优化？
>答：
>   - Vue.js2.x中通过标记静态根节点，优化diff的过程
>   - Vue.js3.0中标记和提升所有的静态根节点，diff的时候只需要对比动态节点内容
>       - Fragments（升级vetur插件）
>       - 静态提升
>       - Patchflag
>       - 缓存事件处理函数

#### 5、Vue.js 3.0 响应式系统的实现原理？
>答：
>   - Vue3 使用 Proxy 对象重写响应式系统，这个系统主要有以下几个函数来组合完成的：
>       - reactive：接收一个参数，判断这参数是否是对象。不是对象则直接返回这个参数，不做响应式处理；创建拦截器对象 handler, 设置 get/set/deleteProperty；返回 Proxy 对象
>       - effect: 接收一个函数作为参数。作用是：访问响应式对象属性时去收集依赖。如果没有 activeEffect，则说明没有创建 effect 依赖；如果有 activeEffect，则去判断 WeakMap 集合中是否有 target 属性。
>       - track：接收两个参数：target 和 key
>       - trigger：判断 WeakMap 中是否有 target 属性