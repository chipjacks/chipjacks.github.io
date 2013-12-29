---
layout: default
title: Posts 
---

<div id="home">
  <h2>Posts</h2>
  <ul class="posts">
    {% for post in site.categories.posts %}
      <li><span>{{ post.date | date: "%B %Y" }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
