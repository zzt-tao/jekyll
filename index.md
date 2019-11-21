---
layout: muban
head: "./css/head.css"
zhuti: "./css/zhuti.css"
---

<div class="head">
	<div class="head_img">
		<div></div>
	</div>
	<div class="head_text">
		<img class="me_img donghua" src="./img/logo.jpg">
		<div class="donghua" style="font-size: 42px;animation-delay:0.4s;">你 好, 我 叫 张 梓 涛</div>
		<div class="donghua" style="font-size: 24px;font-weight: 100;margin:1% auto;animation-delay:0.8s;">欢迎你来到我的博客</div>
	</div>
</div>

<div class="row-md-12" style="margin-top:50px;" >
{% include leibiao.html %}

<div class="col-md-8">

	{% for post in site.posts %}
		<a href="{{ post.url }}">
			<div  class="wenzhang">
				<h4>{{post.title}}</h4>
				<p>{{ post.xiao_title }}</p>	
				<p class="time">2019-11-19</p>
			</div>
		</a>
	{% endfor %}
	<!-- <div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div>
	<div  class="wenzhang">
		<h4>我的第一篇博客文章</h4>
		<p>简介：第一次写博客文章，述说一些小小的心得，以作纪念。</p>	
		<p class="time">2019-11-19</p>
	</div> -->
	
</div>

</div>
