


### Composition API

### 生命周期钩子函数
![](../code/img_C_api/1.png)

### reactive-toRefs-ref
reactive/toRefs/ref

reactive 把对象转换为响应式对象，是一个代理对象

toRefs 把对象的每一个属性都改为响应式数据，可以解构
return toRefs(position)

ref 参数如果传递的是对象的话，他内部其实就是调用 reactive 
如果是基本类型的值，0；他内部会创建一个具有value的对象，在geter中收集依赖，在seter中触发更新

### computed
![](../code/img_C_api/2.png)


### watch
Watch
- Watch的三个参数
    - 第一个参数：要监听的数据
    - 第二个参数：监听到数据变化后执行的函数，这个函数有两个参数分别是新值和旧值
    - 第三个参数：选项对象，deep和immediate
- Watch的返回值
    - 取消监听的函数

跟以前的不一样的地方是，第一个不是 字符串
watch(question, async (newValue, oldValue) => {  })

### watchEffect
WatchEffect
- 是watch函数的简化版本，也用来监视数据的变化
- 接收一个函数作为参数，监听函数内响应式数据的变化

把变化后的数据放到 本地储存中 使用 WatchEffect 会非常的方便

### todolist
#### 功能演示
待办事项清单

ToDoList功能列表
- 添加待办事项
- 删除待办事项
- 编辑待办事项
- 切换待办事项
- 存储待办事项

#### 项目结构

#### 添加待办事项

#### 删除待办事项

#### 编辑待办事项
##### 编辑文本框获取焦点
编辑待办事项
- 双击待办项，展示编辑文本框
- 按回车或者编辑文本框失去焦点，修改数据
- 按esc取消编辑
- 把编辑文本框清空按回车，删除这一项
- 显示编辑文本框的时候获取焦点

#### 切换待办事项
##### 演示效果

#####  改变待办事项完成状态

##### 切换状态

##### 其它

#### 储存待办事项