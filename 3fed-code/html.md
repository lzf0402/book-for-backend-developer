# 编写页面结构

> ftl文件，其实是在html的语法中，插入java数据以及一些逻辑处理，最终解析返回的是html文件，先介绍html编写；

### 页面基本结构

```
<!DOCTYPE html>
<html>
<head>
<!-- 这里是网页头，不会在可视区域显示 -->
<meta charset="utf-8"/>
<title>这里是标题</title>
<meta name="keywords" content="关键字"/>
<meta name="description" content="页面描述"/>
<meta name="viewport" content="width=device-width"/>
<link rel="stylesheet" href="css/style.css"/>
<link rel="shortcut icon" href="img/favicon.ico"/>
</head>
<body>
<!-- 网页实际展示的内容 -->
<h1>常用标签,我是h1,我还有几个兄弟，h2、h3、h4、h5、h6</h1>
<p>我是段落标签，<span style="color:#f00;">我是span标签，默认不换行</span>	</p>

<h2>下面是个无序列表</h2>
<ul>
	<li>Coffee</li>
   	<li>Tea</li>
   	<li>Milk</li>
</ul>

<h2>下面是个有序列表</h2>
<ol>
	<li>2017年销售额150亿rmb</li>
	<li>2016年销售额50亿rmb</li>
	<li>2015年销售额10亿rmb</li>
</ol>

<h2>下面是个简易表单</h2>
<div class="m-form">
    <form name="" action="#" method="get">
        <div class="formitm">
            <label class="lab">姓名：</label>
            <div class="ipt">
                <input type="text" /><span class="domain">中文</span>
            </div>
        </div>
        <div class="formitm">
            <label class="lab">性别：</label>
            <div class="ipt">
                <input type="radio" name="sex" value="0" /><label class="lab">男</label>
                <input type="radio" name="sex" value="1" /><label class="lab">女</label>
            </div>
        </div>
        <div class="formitm">
            <label class="lab">学历：</label>
            <div class="ipt">
            	<select>
            		<option value="0">本科</option>
            		<option value="1">硕士</option>
            		<option value="2">高中</option>
            		<option value="3">博士</option>
            	</select>
            </div>
        </div>
        <div class="formitm">
            <label class="lab">爱好：</label>
            <div class="ipt">
                <input type="checkbox" value="0" /><label class="lab">画画</label>
                <input type="checkbox" value="1" /><label class="lab">游泳</label>
            </div>
        </div>
        <div class="formitm formitm-1"><button class="u-btn" type="button">提交</button></div>
    </form>
</div>

<h2>下面是表格</h2>
<table border="1">
  <tr>
    <th>季度</th>
    <th>销量</th>
  </tr>
  <tr>
    <td>Q1</td>
    <td>$100</td>
  </tr>
  <tr>
    <td>Q2</td>
    <td>$300</td>
  </tr>
</table>

<!-- 在页脚引入入口脚本 -->
<script src="${jspro}page/index.js"></script>
</body>
</html>

```

[html标签大全](http://www.w3school.com.cn/tags/index.asp)


### ftl常用语法

#### 插值

```
<div class="err">${errMsg!''}</div>
```
`!`后面设置为空时的默认值

#### 逻辑判断与遍历

```
<select name="settleMonth" id="settleMonth">
	<option value="">全部</option>
	<#if (monthList![])?size gt 0>
		<#list monthList as month>
        <option>${month}</option>
        </#list>
    <#else>
    	<option>数据为空</option>
    </#if>
</select>

```

##### 宏
定义宏：

```
<#macro title text>
	<title>${text}-网易考拉海购拉客推广平台</title>
</#macro>

```
调用宏：
```
<@title text="首页"/>
```
[freemarker手册](/FreeMarker_Manual_zh_CN.pdf)
