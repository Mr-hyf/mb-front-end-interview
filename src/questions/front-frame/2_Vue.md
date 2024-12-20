# Vue

## vue3和vue2的区别

#### 类型：`基础`

#### 级别：`W1`、`W2`、`W3`、`W4`、`W5`、`W6`

#### 解答（11 分）

* **1：** 源码组织方式变化：使用 TS 重写
* **1：** 支持 Composition API：基于函数的API，更加灵活组织组件逻辑（vue2用的是options api）
* **1：** 响应式系统提升：Vue3中响应式数据原理改成proxy，可监听动态新增删除属性，以及数组变化
* **1：** 编译优化：vue2通过标记静态根节点优化diff，Vue3 标记和提升所有静态根节点，diff的时候只需要对比动态节点内容
* **1：** 打包体积优化：移除了一些不常用的api（inline-template、filter）
* **1：** 生命周期的变化：使用setup代替了之前的beforeCreate和created
* **1：** Vue3 的 template 模板支持多个根标签
* **1：** Vuex状态管理：创建实例的方式改变,Vue2为new Store , Vue3为createStore
* **1：** Route 获取页面实例与路由信息：vue2通过this获取router实例，vue3通过使用 getCurrentInstance/ userRoute和userRouter方法获取当前组件实例
* **1：** Props 的使用变化：vue2 通过 this 获取 props 里面的内容，vue3 直接通过 props
* **1：** 父子组件传值：vue3 在向父组件传回数据时，如使用的自定义名称，如 backData，则需要在 emits 中定义一下

## watch 和 watchEffect 的区别？

#### 类型：`基础`

#### 级别：`W1`、`W2`、`W3`、`W4`、`W5`、`W6`

#### 解答（3分）

* **1：** watch ：既要指明监视的数据源，也要指明监视的回调。

* **1：** watchEffect 可以自动监听数据源作为依赖。不用指明监视哪个数据，监视的回调中用到哪个数据，那就监视哪个数据。

* **1：** watch 可以访问改变之前和之后的值，watchEffect 只能获取改变后的值。

## 如何实现 Vue 组件的插槽（slot）？有哪些类型的插槽？

#### 类型：`基础`

#### 级别：`W1`、`W2`、`W3`、`W4`、`W5`、`W6`

#### 解答（1分）

* **1：** 默认插槽、具名插槽、作用域插槽

## 简述 Vuex 的核心概念和工作流程。

#### 类型：`基础`

#### 级别：`W1`、`W2`、`W3`、`W4`、`W5`、`W6`

#### 解答（2分）

* **1：** 核心概念:<br/> 
&emsp;State：存储应用的状态数据，是一个单一的数据源，所有组件都可以访问, <br/>
&emsp;Mutations：用于同步修改 State 中的数据。
是唯一允许修改 State 的地方，它接收 State 作为第一个参数。<br>
&emsp;Actions：用于处理异步操作，如异步数据获取等，它不能直接修改 State，而是通过提交 Mutations 来间接修改。<br/>
&emsp;Getters(类似于计算属性，用于从 State 中派生出一些新的数据，方便组件获取和使用)
* **1：** 工作流程：<br/>组件通过 dispatch 方法触发 Actions，Actions 中可以进行异步操作，然后通过 commit 提交 Mutations，
Mutations 同步修改 State 的数据，组件可以通过 mapState、mapGetters 等辅助函数获取 State 和 Getters 中的数据，从而实现数据的响应式变化
和组件的更新。