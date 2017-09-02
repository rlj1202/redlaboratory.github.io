---
layout: page
---

<center><h1>아카이브</h1></center>
{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%Y년 %m월'" %}

{% for yearmonth in postsByYearMonth %}

<h2>{{ yearmonth.name }}</h2>

<ul>
{% for post in yearmonth.items %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

{% endfor %}