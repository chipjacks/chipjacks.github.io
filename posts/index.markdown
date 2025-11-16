---
layout: default
title: "Posts"
description: "Browse my latest blog posts and articles on software development, technology, and programming."
---

<div id="home" class="content">
  <div class="post-list">
    {% for post in site.categories.posts %}
			<a class="post-li" href="{{ post.url }}" target="_blank">
				{% if post.preview %}
					<div class="pl-preview">
						<img src="{{ post.preview }}"/>
					</div>
				{% endif %}
				<div class="pl-date">
					{{ post.date | date: "%B %Y" }}
				</div>
				<div class="pl-title">
					{{ post.title }}
				</div>
				<div class="pl-snippet">
					{{ post.snippet }}
				</div>
			</a>
    {% endfor %}
</div>
