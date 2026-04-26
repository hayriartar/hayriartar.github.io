---
layout: default
title: Photos
tag: photos
permalink: /tag/photos/
---



{% include meta-index.html %}



<ul class="archive-list">

{% assign filtered = site.posts | where_exp: "post", "post.tags contains page.tag" %}
{% assign years = filtered | group_by_exp: "post", "post.date | date: '%Y'" %}
{% assign years = years | sort: "name" | reverse %}

{% for year in years %}
  <span class="sene">{{ year.name }}</span>
  <ul>
    {% assign posts = year.items | sort: "date" | reverse %}
    {% for post in posts %}
      <li>
        <a href="{{ post.url | relative_url }}">
          {{ post.date | date: "%Y-%m-%d" }}
          {% unless post.title == "" %} - {{ post.title }}{% endunless %}
        </a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

</ul>