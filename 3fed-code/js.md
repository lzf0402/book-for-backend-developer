# 页面入口js

> 每个页面会有一个入口js文件，在此文件中实现页面的业务逻辑，比如发起异步请求、给dom元素绑定事件、控制UI展示等，入口文件里也可能会去调用封装的方法或组件；

### 常规入口脚本展示

```
/**
 * API接口页面
 * author xxx(xxx@xxx.com)
 */

define([
    'base/klass',
    'base/util',
    'base/event',
    'base/element',
    'util/tab/tab',
    'pro/widget/module',
    './components/dialog'
],
    function(_k, _ut, _v, _e, _tab, Module,Dialog, _p) {
        var pro;

        _p._$$APIModule = _k._$klass();
        pro = _p._$$APIModule._$extend(Module);

        pro.__init = function(_options) {
            this.__supInit(_options);
            this.__initEvent();
            this.__initComponent();
        };

        pro.__initEvent = function() {
            //  进行事件绑定
            _v._$addEvent('id', 'click', this.__selectUserName._$bind(this));
        };

        pro.__selectUserName = function(){
            // 业务逻辑
            // 调用组件
            var dialog = new Dialog({
                title:'xxx'
            });
            dialog.$show();

        }

        _p._$$APIModule._$allocate();
    });

```

#### 进阶- 组件开发

> 目前大部分后台系统的组件化开发，都用了regular框架，对于这部分内容，希望大家有组件的概念，了解如何调用组件，能大致看懂组件的功能逻辑，编写组件还是由我们前端开发来完成。如果有兴趣的同学，可以学习下[进阶篇](/4regularjsji-chu.html)