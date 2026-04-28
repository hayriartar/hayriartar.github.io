---
layout: default
title: Siir
tag: siir
permalink: /tag/siir/
---



{% include meta-index.html %}



<ul class="archive-list">
{% assign filtered = site.posts | where_exp: "post", "post.tags contains page.tag" %}
{% assign posts = filtered | sort: "date" | reverse %}
{% for post in posts %}
  <li>
    <a href="{{ post.url | relative_url }}" class="archive-link">
      <span class="archive-title">{% unless post.title == "" %}{{ post.title }}{% endunless %}</span>
      <span class="archive-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    </a>
  </li>
{% endfor %}
</ul>