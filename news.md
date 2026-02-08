---
title: News
permalink: /news/
---

### **Lab News**



<div class="content list">
<div class="list-item">
<p class="list-post-title">
</p>
</div>
  {% for post in site.posts %}
    {% if post.categories contains 'blog' %}
    <div class="list-item">
    <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a> (<small>{{post.date | date: "%m/%d/%y" }}</small>)
        </p>
    </div>
    {% endif %}
  {% endfor %}
</div>
