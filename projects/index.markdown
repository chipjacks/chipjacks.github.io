---
layout: default
title: "Projects"
---
<meta http-equiv="refresh" content="0; url=/posts">

<div id="home" class="content">
	<div class="page-title">
  	Projects
	</div>
  <ul class="post-list">
    {% for post in site.categories.projects %}
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
