## 第一章 课程导学
基础内容--环境搭建--基础语法---原理进阶--动画
redux--redux进阶

实战项目--环境搭建--header--首页---详情页
登录校验--上线流程

技术点包含：
create-react-app搭建
组件化思维
jsx语法
开发调试工具
虚拟DOM
生命周期
React-transition-group解决动画效果
Redux
Antd
UI,容器组件
无状态组件
react-thunk
redux-saga
styled-components
immutable
redux-immutable
axios

课程收货：
彻底入门react的使用
完整了解react的工具全家桶
上手大型项目的前端开发
规范的代码编写

## 第二章 React初探
2-1React简介 官网：https://reactjs.org/
2-2React开发环境准备 
1）引入.js文件来使用React
2）通过脚手架工具来编码
3）create-react-app  https://reactjs.org/docs/create-a-new-react-app.html
node、npm安装
sudo cnpm install create-react-app -g 全局安装create-react-app
2-3工程目录文件简介 
2-4react中的组件
2-5React中最基础的JSX语法

## 第三章 React基础精讲
3-1使用React编写TodoList功能
  ``` Fragment 占位符 ，可以省略最外层标签```
3-2React中的响应式设计思想和事件绑定
3-3实现TodoList新增删除功能
  ``` immutable state 不允许我们做任何的改变```
3-4JSX语法细节补充
  ``` label和input做光标聚焦，可以在label上加htmlFor与input的id一致 ```
<label htmlFor="insertArea"> 输入内容</label>
 <input id="insertArea" />
<!-- 样式展示处理 -->
import './style.css'
  className="input"

  .input{
  border: 1px solid red;
} 
<!-- --------------------------- -->
3-5拆分组件与组件之间的传值
3-6TodoList代码优化
``` 1)一般我们把用bind去处理this指向的绑定放在constructor下，组件初始化的时候就把this处理好，下面就不用再修改它了;当然也可以采用箭头函数去处理 ```
如：
 super(props);
 this.handleItemDelete = this.handleItemDelete.bind(this); // 这样写可以节约性能

``` 2)在render中代码较多的时候，可以适当的做代码拆分；此处将TodoItem进行代码拆分。如在TodoList中的getTodoItem方法获取到的就是原来的div包起来的子组件内容 ```

``` 3)注意：在最新版的语法中，setState可以接受一个函数。 ```
如：
    // 原
    // this.setState({ 
    //   inputValue: e.target.value
    // })
    // 注意：在最新版的语法中，setState可以接受一个函数。
    const value=e.target.value;
    this.setState(()=>({ // 写成函数就是个异步，需要在上面对value做保存
      inputValue: value
    })) ```

3-7围绕React衍生出的思考
react是声明式开发，面向数据编程，会根据这个数据去构建，减少DOM操作
以前jquery是命令式，需要告诉一步一步怎么做
父组件向子组件传入参数数据，子组件不能改变父组件的数据。要想改变父组件的数据，调用父组件传过来的方法，最后也是由父组件去改变数据，react是单向数据流的框架
组件之间的复杂传值，就需要用到redux/flux等工具
react函数式编程：
1、维护起来比较容易
2、便于自动化测试
## 第4章 React高级内容
4-1Reactdevelopertools安装及使用
4-2PropTypes与DefaultProps的应用
PropTypes 可以规定传进来的参数类型，DefaultProps可以对组件设置默认参数
``` test: PropTypes.string.isRequired, // 如果必填，报错：Failed prop type: The prop `test` is marked as required in `TodoItem`, but its value is `undefined`. ```
``` TodoItem.defaultProps={ test:'hello world'  // 组件可以设置默认值，如果父组件没有传对应的属性，可以定义默认值 } ```
4-3props，state与render函数的关系
  当组件的state或者props发生改变的时候，render函数就会重新执行
  当父组件的render函数被运行时，它的子组件的render都会将重新运行
4-7React中ref的使用
 ``` ref={(input)=>this.input=input}  const value=this.input.value// 用ref是操作DOM  尽量不要直接操作DOM```
4-8React的生命周期函数
4-9React生命周期函数的使用场景
4-10使用Charles实现本地数据mock
4-11React中实现CSS过渡动画
## 第5章Redux入门
5-1Redux概念简述



 Redux=Reducer+Flux
