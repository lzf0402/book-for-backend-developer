# 工程介绍 - CPS系统

### cps网盟系统

* [cps前台](http://cps.kaola.com/)
* [cps后台](http://cps.kaola.com/backend/index)

网盟系统`分前后台`

#### 工程目录：

![](/assets/cps.png)

前端文件位于工程中的`src/main/webapp`目录下，主要包括：

#### 目录结构说明：

![](/assets/cps2.png) 


#### css预处理器——mcss
> 因为css本身抽象能力不足，所以业界出现了很多预处理器（知名的如SASS，LESS，以及我们常用的MCSS等），来强化css的功能；

编写page.mcss ——> page.css ——> ftl里引入css文件


#### readme

> 关于工程相关信息，都在其readme文件里有详细说明


#### 安装下工程依赖包

在有package.json的同级目录下，命令行执行如下：
```
$ npm install
```

#### 维护与开发工作：

维护：
- 找到功能页面的ftl文件，在上面添加修改标签
- 找到页面的入口js脚本，添加修改相关功能逻辑
- 在入口脚本里找到组件路径，修改组件的html模板及js实现部分

新加功能：
- 新建一个ftl文件（可以拷贝一个已有的文件，在其基础上修改）
- 新建一个js文件，在ftl里引入，作为该页面的入口脚本
- 新建一个mcss文件，作为此页面都有的样式，公用的样式放在module.mcss中


* 开发一个页面需要修改的主要文件是：`WEB-INF/template`下的ftl文件，和`src/javascript/page`下的页面相关js；
其他目录主要为公用组件，一般情况下，不建议修改，如果需要修改，可以找前端确定下；


* 【注】
前台系统在用户登录后，采用了[nej的单页应用方式](https://github.com/genify/nej/blob/master/doc/DISPATCHER.md)
其中page/main.js是单页应用的入口脚本，配置了路由关系
各个功能模块在src/html目录下

