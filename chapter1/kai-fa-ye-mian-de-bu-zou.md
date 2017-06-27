# 开发页面的步骤

> 在开始这步前，请确定已经按照完成了“2.1开发前的准备工作”提到的依赖工具的安装；

第一步：定义访问页面的url；

第二步：在工程的`src/main/webapp`目录下确定有`.nekrc`文件，如果有执行`nek build -u url`命令；这个命令会按照我们的规范，生成基础的ftl、js、html目录到对应的目录下；这时就可以正式开发代码了；

第三步：生成的ftl基本不用变，所以大部分情况下，可以跳过写ftl的步骤；但是如果需要获取同步数据，则需要在ftl下面加一段script， 如下，需要注意的地方是noparse注释不要去掉，因为这个是打包不解析标记，如果没有，这段script会被打包到js里面，js无法识别${}这种ftl的语法，运行时会报错；

```
    <!--@noparse-->
    <script>
    window.config = {
        judgeStateList: ${stringify(judgeStateList!{})},
        judgeResultList: ${stringify(judgeResultList!{})},
        storageList: ${stringify(storageList!{})},
    }
    </script>
    <!--/@noparse-->
    <script src="${nejRoot}"></script>
    <script>
        NEJ.define([
            'pro/page/aftersales/index/entry'
        ],function(m){
            m._$$Module._$allocate();
        });
    </script>
```

第四步：找到页面的js目录，开始搭建页面的html结构和编码业务逻辑的js；

至此，应该了解的东西：

1. 前端页面都有哪些文件？
2. 对应文件放在什么位置？
3. 各种文件类型承担的作用？
4. nek工具创建页面的使用方法？



