---
layout: archive
title: "Notes on research and work"
permalink: /blog/
author_profile: false
classes: wide
---

<style>
  .entries-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1rem;margin-top:.5rem}
  .entry-card{border:1px solid rgba(0,0,0,.08);border-radius:12px;overflow:hidden;background:#fff}
  .entry-card a{text-decoration:none;color:inherit;display:block}
  .entry-card img{width:100%;display:block}
  .entry-title{font-size:1.05rem;margin:.6rem .75rem 0}
  .entry-excerpt{margin:.25rem .75rem .5rem;color:#444}
  .entry-date{display:block;margin:.25rem .75rem 1rem;color:#777;font-size:.9rem}
</style>

{% assign docs = site.blog | sort: "date" | reverse %}
<div class="entries-grid">
{% for post in docs %}
  {% assign teaser = post.header.teaser | default: site.teaser %}
  <article class="entry-card">
    <a href="{{ post.url | relative_url }}">
      {% if teaser %}<img src="{{ teaser | relative_url }}" alt="{{ post.title | escape }}">{% endif %}
      <h2 class="entry-title">{{ post.title }}</h2>
      {% if post.excerpt %}<p class="entry-excerpt">{{ post.excerpt | strip_html | strip_newlines }}</p>{% endif %}
      <span class="entry-date">{{ post.date | date: "%b %-d, %Y" }}</span>
    </a>
  </article>
{% endfor %}
</div>
