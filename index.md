---
layout: home
permalink: "/"
---

<div class="hero-body" >
		<div class="container">
			<h1 class="title">Post</h1>
			<hr>
				{% for post in site.posts %}
					<br>
					<h3  class="title is-3">
						<a href="{{post.url | prepend: site.baseurl}}" style="color: #145ea8;"> 
							{{post.title}}
						</a>
					</h3>	
					<h3 class="subtitle">
						<span class="post-meta"> 
							{{ post.date | date: "%b %-d, %Y" }}
						</span>
					</h3>
					<br>
				{% endfor %} 
		</div>
</div>