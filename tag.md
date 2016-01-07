---
layout: page
title: Tag
permalink: /tag/
---

Click on a tag to see relevant list of posts.

<ul class="tag-list">
{% for tag in site.tags %}
  {% assign t = tag | first %}
  <li><a href="/tag/#{{t | downcase | replace:" ","-" }}">{{ t | downcase }}</a></li>
{% endfor %}
</ul>

---

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<h3><a name="{{t | downcase | replace:" ","-" }}"></a><a href="/tag/#{{t | downcase | replace:" ","-" }}">{{ t | downcase }}</a></h3>
<ul class="post-list">
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y"  }}</span>
  </li>
  {% endif %}
{% endfor %}
</ul>

---

{% endfor %}
