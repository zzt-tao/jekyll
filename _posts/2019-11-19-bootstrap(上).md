---
layout: post
css: ["css/public.css"]
sosuo: false
title: bootstrap的笔记(上)
xiao_title: 之前已经学过bootstrap了，现在由于1+X证书考证需要，复习并记录一些类和方法。
tag: [Bootstrap]
---

# bootstrap笔记
	
## bootstrap移动设备优先
	
1. Bootstrap 是移动设备优先的，所以为了确保适当的绘制和触屏缩放，需要在 `<head>` 之中添加 **viewport** 元数据标签。
```html
	<meta name="viewport" content="width=device-width, initial-scale=1">
```

1. 在移动设备浏览器上，通过为视口（viewport）设置 meta 属性为 user-scalable=no 可以禁用其缩放（zooming）功能。这样禁用缩放功能后，用户只能滚动屏幕，就能让你的网站看上去更像原生应用的感觉。注意，这种方式我们并不推荐所有网站使用，还是要看你自己的情况而定！
```html
	<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
```

## 布局容器

Bootstrap需要为页面内容和栅栏系统包裹一个 `.container` 容器。就是在页面内容和栅栏系统之前要加上这个容器。

1. `container` 类用于固定宽度并支持响应式布局的容器。
```html
	<div class="container"> ... </div>
```

2. `container-fluid` 类用于100%宽度，占据全部视口的容器。
```html
	<div class="container-fluid"> ... </div>
```
**注意：由于`padding`等属性，两种容器不能互相嵌套**

## 栅格系统

### 栅格参数
**注意：列需要放到`.row`中，并且`.row`外需要有`.container`容器，而如果希望变成流式布局（即百分比布局）,就要将`.container`改为`.container-fluid`**
1. `.col-xs-` **超小屏幕** 手机设备 (<768px)
2. `.col-sm-` **小屏幕** 平板电脑 (>=768px)
3. `.col-md-` **中等屏幕** 桌面显示器 (>=992px)
4. `.col-lg-` **大屏幕** 大桌面显示器 (>=1200px)

### 实例应用
1. 多个设备之间融合，一个元素可以写多个设备的栅格类。
```html
<div class="row">
  <div class="col-xs-12 col-sm-6 col-md-8">.col-xs-12 .col-sm-6 .col-md-8</div>
  <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
</div>
<div class="row">
  <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
  <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
  <div class="clearfix visible-xs-block"></div>
  <div class="col-xs-6 col-sm-4">.col-xs-6 .col-sm-4</div>
</div>
```
2. 多余的列将另起一行排序
3. 列偏移：.col-md-offset-*
4. 列排序：.col-md-push-* 数字大的在前面。

## 排版标签
```html
class
<p class="lead">lead类可以让段落突出显示</p>
<p class="text-left">左对齐</p>
<p class="text-right">右对齐</p>
<p class="text-center">居中对齐</p>
<p class="text-lowercase">首字母大写</p>
<p class="text-uppercase">全部大写</p>
<p class="text-capitalize">每个单词大写</p>
```

## 表格
1. **`.table-striped`**类可以给`<tbody>`之内的每一行增加斑马条纹样式。
1. **`.table-bordered`**类可以为表格和其中的每个单元格增加边框
1. **`.table-hover`**类可以给`<tbody>`添加鼠标悬停样式
1. **`.table-condensed`**类可以让表格更加紧凑。
### 表格行或单元格状态类
1. **`.active`** ：鼠标悬停在行或单元格上所设置的颜色
1. **`success`** ：标识成功
1. **`info`** ：标识普通的提示信息或动作
1. **`warning`** ：标识警告或需要用户注意
1. **`danger`** ：标识危险或错误
响应式表格：将`.table`元素包裹在`.table-responsive`元素内，即可创建响应式表格。

## 按钮
- **`.btn`** 按钮类
### 颜色
- **`.btn-default`** 按钮默认样式，白灰色
- **`.btn-primary`** 首选项，深蓝色
- **`.btn-success`** 成功，绿色
- **`.btn-info`** 一般信息样式，浅蓝
- **`.btn-warning`** 警告样式，黄色
- **`.btn-danger`** 危险样式，红色
- **`.btn-link`** 链接样式，像a标签一样
### 尺寸
- **`.btn-lg`** 最大按钮
- **`.btn-primary`** 默认尺寸
- **`.btn-sm`** 小按钮
- **`.btn-xs`** 超小按钮
- **`.btn-block`** 块级元素按钮，100%宽度
### 其它
- **`.active`** 激活状态按钮，底色更深、边框夜色更深、向内投射阴影。
- 按钮的**`disabled`** 属性为禁用状态按钮，无法选中点击。(只能应用于按钮元素)
- **`.disabled`**类，禁用状态，可以为其它元素添加此类样式做到禁用效果(案例为a标签)

## 图片
- **`.img-responsive`** 响应式图片样式
- **`.img-rounded`** 图片圆角样式
- **`.img-circle`** 圆形图片样式
- **`.img-thumbnail`** 图片添加外边框样式
 
## 辅助类
### 文本背景类
- **`.bg-primary`** 蓝色背景
- **`.bg-success`** 浅绿色
- **`.bg-info`** 浅蓝色
- **`.bg-warning`** 浅粉红色
- **`.bg-danger`** 浅红色
### 快速浮动
- **`.pull-left`** 左浮动
- **`.pull-right`** 右浮动
- **`.clearfix`** 清除浮动
### 其它
- **`.center-block`** 内容居中
- **`.show`** 显示内容
- **`.hidden`** 隐藏内容

## 响应式工具类
- **`.visible-xs-*`** 超小屏幕 手机(<768px) 可见; 
- **`.visible-sm-*`** 小屏幕 平板(>=768px && <992px) 可见;
- **`.visible-md-*`** 中等屏幕 桌面(>= 992px && <1200px) 可见;
- **`.visible-lg-*`** 大屏幕 桌面(>=1200px) 可见;
- 注释：若未加-* 则和该类为相反区间。例如：**`.visible-xs`** 为>=768px 可见，<768px隐藏。
- **`.visible-*-block`** 类为display:block;
- **`.visible-*-inline`** 类为display:inline;
- **`.visible-*-inline-block`** 类为display:inline-block;
- 注释：*表示(xs/sm/md/lg)






