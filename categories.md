---
layout: default
permalink: /categories/
---

<div class="box">
	<center><h1>카테고리 목록</h1></center>
	{% for category0 in site.categories %}
		{% assign b = false %}
		{% for post in site.posts %}
			{% if post.categories[0] == category0.first %}
				{% assign b = true %}
			{% endif %}
		{% endfor %}
		{% if b == true %}
			<h2><a href="/{{ category0 | first }}">{{ category0 | first }}</a></h2>
			
			<ul>
			{% for category1 in site.categories %}
				{% assign b = false %}
				{% for post in site.posts %}
					{% if post.categories[0] == category0.first and post.categories[1] == category1.first %}
						{% assign b = true %}
					{% endif %}
				{% endfor %}
				{% if b == true%}
					<li><a href="/{{ category0 | first }}/{{ category1 | first }}">{{ category1 | first }}</a></li>
				{% endif %}
			{% endfor %}
			</ul>
		{% endif %}
	{% endfor %}
</div>