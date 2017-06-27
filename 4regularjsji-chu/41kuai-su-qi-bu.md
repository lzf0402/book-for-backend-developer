# 快速起步

> 示例：[http://regularjs.github.io/guide/zh/intro/hello-regularjs.html](http://regularjs.github.io/guide/zh/intro/hello-regularjs.html)

[Demo](http://fiddle.jshell.net/leeluolee/C2Gh9/1/)

1. 通过script引入Regularjs；引入后，就可以直接通过Regular变量访问到Regular对象了；
2. 工程所有的组件都是Regular.extend出来的，为了提取一些通用的东西，我们又封装了BaseComponent， BaseComponent继承于Regular，工程中所有组件都从BaseComponent进行扩展；

   ```
    ![](/assets/components.jpg)
   ```

3. 几个关键属性和方法

```
template: 组件的模板
data: component组件的初始化状态
$inject方法：会将组件插入到目标节点的位置
{}插值：模板的语法，可以显示data中配置的数据
```

## 总结

虽然这个例子非常简单，但是基本上实现一个组件的思路大同小异

1. 根据需求得到静态html结构，并将其模板化，并结合Regular.extend将其封装成一个组件。
2. 如果需要你还可能将部分可重用功能拆分为子组件；



