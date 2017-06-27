# 前端文件规范

## 背景

如果发现某个页面有问题，需要修改它的代码；之前都是要根据url，找到对应的controller，在controller中找到这个url返回的ftl模板是哪个，搜索这个模板路径，再找script，看它的页面入口js脚本在哪里；这样找文件，很麻烦；因此我们定义了一套文件路径规范，目的是看到url，就能立马找到这个页面的ftl模板路径，以及对应的全部脚本的位置；

## 规范

> 详细规则参见：[文档](https://note.youdao.com/share/?token=F744ACDC19CA45B2949DBBD4696C19C2&gid=31842585#/)

以进销存为例，假设nei中定义了两个页面，url为：`/backend/sku/manage/index`和`/backend/sku/manage/detail`

那么对应的ftl路径应该为：

![](/assets/popo_2017-06-23  10-23-55.jpg)

对应的js资源路径应该为：

![](/assets/popo_2017-06-23  10-25-15.jpg)

我们还规范了js目录内部的结构：

![](/assets/popo_2017-06-23  10-27-46.jpg)

## 其他

1. 目录命名以`.`点符号间隔， 如之前命名为fixedColumn的改为column.fixed； 名词提前；代码里的变量命名还是驼峰；
2. 为了生成更简单的结构，定接口时要特别注意下url，去除不必要的名称，每级驼峰单词最多两个；

## 注意问题

由于每个工程可能最开始没有统一，ftl目录的名称有的叫views有的叫pages， 有的叫page， 如果生成的路径不对，则需要修改`.nekrc配置文件`；

## 总结

这个目录结构我们有nek工具，执行`nek build -u url`命令就可以生成这样规范的结构，并不需要把所有细节都记住；这里只是解释清楚为什么要定义这样的规范；我们还开发了快速获取js、ftl路径的工具，在使用nekui的页面上，按下ctrl+alt+shift+c快捷键可以将js的路径copy到剪贴板，直接在idea中，查找复制路径即可定位到对应文件；相应的、输入`ctrl+alt+shift+d`快捷键可以获取到ftl的路径；

