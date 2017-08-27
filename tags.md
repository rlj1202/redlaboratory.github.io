---
layout: default
permalink: /tags/
---

<div class="box">
<center><h1>태그목록</h1></center>
{% for tag in site.tags %}
	<h2 id="{{ tag | first }}">{{ tag | first }}</h2>
	{% assign tag_posts = tag | last %}
	<ul>
	{% for post in tag_posts %}
		<li><a href="{{ post.url }}">{{ post.title }}</a></li>
	{% endfor %}
	</ul>
{% endfor %}
</div>