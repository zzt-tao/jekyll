---
layout: post
css: ["css/public.css"]
sosuo: false
title: bootstrap的笔记(下)
xiao_title: 之前已经学过bootstrap了，现在由于1+X证书考证需要，复习并记录一些类和方法。
tag: [Bootstrap]
---

# bootstrap笔记

## 下拉菜单
### 实例 
菜单触发器和菜单都要包裹在 `.dropdown` 或 `.dropup`里(一个菜单向下，一个向上)，或者拥有 `position:relative;`的元素里。
```html
<div class="dropdown">
  <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
    Dropdown
    <span class="caret"></span>
  </button>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenu1">
    <li><a href="#">Action</a></li>
    <li><a href="#">Another action</a></li>
    <li><a href="#">Something else here</a></li>
    <li role="separator" class="divider"></li>
    <li><a href="#">Separated link</a></li>
  </ul>
</div>
```
小知识：可以将按钮和按钮组的知识添加到菜单触发器里，实现按钮式下拉菜单和分裂式下拉菜单(使用一个按钮组);
### 更多
- 菜单左右对齐：`dropdown-menu-left` 和 `dropdown-menu-right` ;
- `.dropdown-header` 标题样式，应添加在菜单的第一个元素里。
- `.divider`为分割线。
- `.disabled` 为禁用菜单项。(也可以禁用导航栏等)

## 按钮组
- `.btn-group`类为一个按钮组，按钮组之间可以互相嵌套，可以把按钮组放入按钮组中。
- `.btn-toolbar`类为按钮组的父元素，可实现多个按钮组排成一列。
- `.btn-group-lg` 类为最大。
- `.btn-group-sm` 类比默认小。
- `.btn-group-xs` 类为最小，不添加为默认大小。
- `.btn-group-vertical` 类为垂直排序。
- 在类为 `.btn-group` 中添加 `.btn-group-justified` 类就可实现两端对齐。

## 输入框组
- `.input-group`类为输入框组
- `.input-gruop-addon`类可以在输入框前添加提示文本，也可以将其他元素放入其中。如多选框、单选框、按钮、下拉菜单等。
- 尺寸和按钮组一致。

## 导航、导航条和路径导航
`.nav`为导航类，在此类里添加`.nav-justified`实现导航栏两端对齐。
`.nav-tabs`标签式导航栏
`.nav-pills`胶囊式导航栏，`.nav-stacked`让胶囊式导航栏垂直排序。
`.disabled`禁用式的导航链接。
注释：可以在导航栏里添加下拉菜单和表单等。
导航条案例
```html
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
	  //可以在a标签中使用图片。即品牌图标
      <a class="navbar-brand" href="#">Brand</a>
    </div>
	
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
      <ul class="nav navbar-nav">//导航样式
        <li class="active"><a href="#">Link <span class="sr-only">(current)</span></a></li>//active是选中样式
        <li><a href="#">Link</a></li>
		//下拉菜单
        <li class="dropdown">
		  //下拉菜单的触发器，data-toggle是为该元素添加toggle事件(JQ的方法)，role只是为了语义化，aria-haspopup:true表示点击的时候会出现菜单，false表示没有pop-up效果(动画效果)。
		  //aria-expanded:表示展开状态。
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>
          //下拉菜单
		  <ul class="dropdown-menu">
            <li><a href="#">Action</a></li>
            <li><a href="#">Another action</a></li>
            <li><a href="#">Something else here</a></li>
            <li role="separator" class="divider"></li>
            <li><a href="#">Separated link</a></li>
            <li role="separator" class="divider"></li>
            <li><a href="#">One more separated link</a></li>
          </ul>
        </li>
      </ul>
	  //navbar-left为向左浮动
      <form class="navbar-form navbar-left">
        <div class="form-group">
          <input type="text" class="form-control" placeholder="Search">
        </div>
        <button type="submit" class="btn btn-default">Submit</button>
      </form>
	  //navbar-right为向右浮动
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#">Link</a></li>
        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>
          <ul class="dropdown-menu">
            <li><a href="#">Action</a></li>
            <li><a href="#">Another action</a></li>
            <li><a href="#">Something else here</a></li>
            <li role="separator" class="divider"></li>
            <li><a href="#">Separated link</a></li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</nav>
```
- `.navbar-fixed-top` 将导航条固定在顶部。
- `.navbar-fixed-bottom` 将导航条固定在底部。
- `.navbar-static-top` 静止在头部。
- `.navbae-inverse` 导航条黑色。

#### 路径导航
```html
<ol class="breadcrumb">
  <li><a href="#">Home</a></li>
  <li><a href="#">Library</a></li>
  <li class="active">Data</li>
</ol>
```

## 分页
#### 案例
```html
<nav aria-label="Page navigation">
  <ul class="pagination">//pagination-lg/sm可以改变大小
    <li>
      <a href="#" aria-label="Previous">
        <span aria-hidden="true">&laquo;</span>
      </a>
    </li>
    <li><a href="#">1</a></li>
    <li><a href="#">2</a></li>
    <li><a href="#">3</a></li>
    <li><a href="#">4</a></li>
    <li><a href="#">5</a></li>
    <li>
      <a href="#" aria-label="Next">
        <span aria-hidden="true">&raquo;</span>
      </a>
    </li>
  </ul>
</nav>
```
`.disabled`禁止状态，`.active`激活状态
#### 翻页
```html
<nav aria-label="...">
  <ul class="pager">
	//添加`previous`和`next`可以实现两端对齐，(一个靠左一个靠右)
    <li class="previous"><a href="#"><span aria-hidden="true">&larr;</span> Older</a></li>
    <li class="next"><a href="#">Newer <span aria-hidden="true">&rarr;</span></a></li>
  </ul>
</nav>
```

## 标签和徽章
#### 标签实例
```html
<span class="label label-default">Default</span>//默认样式
<span class="label label-primary">Primary</span>//深蓝色
<span class="label label-success">Success</span>//绿色
<span class="label label-info">Info</span>//浅蓝色
<span class="label label-warning">Warning</span>//黄色
<span class="label label-danger">Danger</span>//红色
```
#### 徽章
```html
<span class="badge">42</span>//可以给按钮、链接等添加一个提示。
```
## 巨幕和页头
#### 巨幕实例
```html
<div class="jumbotron">//巨幕
  <div class="container">//取消圆角
    <h1>Hello, world!</h1>
    <p>...</p>
    <p><a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a></p>
  </div>
</div>
```
#### 页头实例
```html
<div class="page-header">//可以有一个上边距。
  <h1>Example page header <small>Subtext for header</small></h1>
</div>
```
## 缩略图和警告框
#### 缩略图实例
```html
<div class="row">
  <div class="col-xs-6 col-md-3">
    <a href="#" class="thumbnail">//缩略图
      <img src="..." alt="...">
    </a>
  </div>
  ...//自己结合之前的知识自由搭配
</div>
```
#### 警告框实例
```html
<div class="alert alert-success" role="alert">...</div>//绿色
<div class="alert alert-info" role="alert">...</div>//蓝色
<div class="alert alert-warning" role="alert">...</div>//黄色
<div class="alert alert-danger" role="alert">...</div>//红色
```
- 可以为警告框添加 `.alert-dismissible`类和关闭按钮
```html
<div class="alert alert-warning alert-dismissible" role="alert">
  //注意：data-dismiss="alert"属性不能缺少
  <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
  <strong>Warning!</strong> Better check yourself, you're not looking too good.
</div>
```
- 可以为警告框中的a标签添加 `.alert-link` 类，会生成相应的a标签链接。