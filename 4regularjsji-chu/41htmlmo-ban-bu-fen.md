# html模板语法

> 官方文档：[http://regularjs.github.io/reference/?syntax-zh](http://regularjs.github.io/reference/?syntax-zh)

### {}插值表达式里面都能写什么？

举个例子，下列表达式在regularjs中都是合法的:

* 100 + ‘b’.
* user? ‘login’: ‘logout’
* title = title + ‘1’
* !isLogin &&this.login\(\)
* items\[index\]\[this.nav\(item.index\)\].method1\(\)

表达式中的变量，如果不带this，都是取的是this.data中的值；一般使用this.xxx调用组件中的方法；

### 一些常用Rule规则语法

* 遍历数组list

```
{#list xxxList as item}
    {item.name}{item_index}
{/list}
```

* if/else/elseif条件控制

```
{#if user.age >= 80 }
  you are too old
{#elseif user.age <= 10}
  you are too young
{#else}
  Welcome, Friend
{/if}

if除了可以控制内容块之外，还可以控制属性，如
<input type="checkbox" {#if selected}checked{/if} />
```

### filter过滤显示的值

```
Regular.filter( "lowercase" , function(obj) {
  return (obj).toLowerCase();
};

//template
<div>{ username | lowercase }</div>

如果需要传参数到filter中，则可以这样写
Regular.filter( "lowercase" , function(obj, num, username) {
  console.log(obj, num, username);
  return (obj).toLowerCase();
};

<div>{ obj | lowercase:1,username }</div>
```



