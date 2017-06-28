# 编写样式 css

> css相当于是网页的外衣，给html结构设置样式；目前工程里已有一些可复用的样式，包括列表、表单、按钮之类的，可复用的样式一般都定义在module.mcss内

### css语法规则

`选择器名称{属性名:属性值}`


### 引入样式方式

```
<!-- 外链样式文件，head标签里引入 -->
<link rel="stylesheet" href="css/style.css"/>
<!-- 内联样式，设置在head标签里  -->
<style type="text/css">
    .tag{
        font-size: 16px;
    }
    #mytag{
        color: red;
    }
    p{
        font-weight: bold;
    }
</style>
<!-- 行内样式 -->
<p class="tag" id="mytag" style="font-size: 12px;color:#00f;">我是段落标签</p>
 
```


### 常用css选择器

- 类选择器 .class{} 最常用
- id选择器 #id{}
- 标签选择器  input{}
- 属性选择器 [type="checkbox"]

[CSS 选择器参考手册](http://www.w3school.com.cn/cssref/css_selectors.ASP)


### 进阶—— MCSS，强化后的css
[MCSS](https://github.com/leeluolee/mcss)是css的预编译器，增强了css的语法功能；

常用的功能

- 嵌套：

```
.m-home{
    display: block;
    li{
        &.itm{
            height:30px;
        }  
    }
}

```

通过mcss编译后输出的css：

```
.m-home{
  display:block;
}
.m-home li.itm{
  height:30px;
}
```

- 变量： 

```
<!-- 定义变量 -->
$white = #fff;

<!-- 使用变量 -->
.m-title{
    color: $white;
}

```

其他功能看官网介绍吧～


### 进阶- css选择器规范

> 前端项目基本遵从[NEC](http://nec.netease.com/standard/css-sort.html)规范，可以在项目中依样画葫芦，参考已有的功能；

选择器命名规范：

- .g- 布局分类，如`.g-footer`,`.g-side`
- .m- 一个大的模块，如`.m-loginform`，`.m-list`
- .u- 一个小的元件，可以嵌套在模块里， 如`.u-btn`, `.u-icon`

