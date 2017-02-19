---
layout: home
---

<div class="section scrollspy">
		<h3 class="header rigth">Post</h3>
</div>

{% for post in site.posts %}
<div class="s12 rigth">
		<div class="section scrollspy">
		<span class="post-meta">•  {{ post.date | date: "%b %-d, %Y" }}</span>
		<h5 class="header"><a href="{{post.url | prepend: site.baseurl}}"> {{post.title}}</a></h5>
			</div>
</div>
{% endfor %}

