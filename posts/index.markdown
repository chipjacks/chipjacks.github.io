---
layout: default
title: Posts 
---

<div id="home" class="content">
	<div class="page-title">
  	Posts
	</div>
  <ul class="post-list">
    {% for post in site.categories.posts %}
			<li class="post-li" onclick="window.location='{{ post.url }}';">
				<div class="pl-title">
					{{ post.title }}
				</div>
				<div class="pl-date">
					{{ post.date | date: "%B %Y" }}
				</div>
				<br>	
				<div class="pl-snippet">
					{{ post.snippet }}
				</div>
			</li>
    {% endfor %}
  </ul>
</div>
