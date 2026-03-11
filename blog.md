---
layout: page
title: Blogs
permalink: /blog/
---

Here are my latest blog posts:

<br>

<div class="blog-list">
  {% for post in site.posts %}
  <div class="working-paper-card">
    <div class="paper-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </div>
    <div class="paper-meta">
      <i class="far fa-calendar-alt"></i> {{ post.date | date: "%B %d, %Y" }}
      {% if post.categories %}
      <span style="margin-left: 15px;">
        <i class="far fa-folder"></i>
        {% for category in post.categories %}
          {{ category }}{% if forloop.last == false %}, {% endif %}
        {% endfor %}
      </span>
      {% endif %}
    </div>
    {% if post.excerpt %}
    <div class="paper-authors">
      {{ post.excerpt | strip_html | truncate: 200 }}
    </div>
    {% endif %}
    <div class="paper-links">
      <a href="{{ post.url | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Read More</a>
    </div>
  </div>
  {% endfor %}

  {% if site.posts.size == 0 %}
  <p>No blog posts yet. Check back soon!</p>
  {% endif %}
</div>
