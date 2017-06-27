# 前端基础

  
![](/assets/fed.png)

### 前端三把斧
  - HTML 结构
  - CSS  表现
  - Javascript 行为

![](/assets/fed2.png)

HTML中用`link`标签引入css文件，用`script`标签引入js文件；


### 服务端模板
  > 常用的如[freemarker](/FreeMarker_Manual_zh_CN.pdf)（`.ftl`文件），由服务端解析，动态整合java中的model对象后，返回给客户端一份静态的html文件；

  ![](http://freemarker.org/images/overview.png)

### 传统的开发模式
  freemarker + model -> html，通过javascript去操作DOM收集数据，发请求获取到数据后再操作DOM，改变UI；

  问题：
  - js既要去获取数据，做功能处理与数据交互，还要去操作表现层，代码会越来越混乱，不利于维护；
  - 结构和业务逻辑耦合，不利于重用


### 数据驱动+组件化开发

  前端的框架
  - [RegularJS](http://regularjs.github.io/guide/zh/index.html) 目前工程里常用
  - [VueJS](https://cn.vuejs.org/v2/guide/)

  借助第三方框架，实现由数据双向绑定来驱动
  js操作数据 ——> 数据改变 <——> UI变化
  抽取组件来实现公用

  一个独立组件包含：
  一个js文件 + 组件的html结构 + 组件自身的css 


### 开发流程

  前后端定义接口 -> 前端根据接口写mock假数据文件 -> 编写ftl文件+css文件 
  -> 编写入口js文件 -> 调用组件或封装组件

