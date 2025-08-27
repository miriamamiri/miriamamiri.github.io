---
layout: single
title: "This is Esmaeil's Website!"
permalink: /
author_profile: false
classes: wide
---

<p align="center">
  <img src="/images/Esmaeil-web.jpg"
       alt="Esmaeil Izadi"
       style="width:230px;height:230px;border-radius:70%;object-fit:cover;box-shadow:0 4px 12px rgba(0,0,0,.08);margin:0.5rem 0 1rem;" />
</p>

<p align="center"><em>I'm an economist. I think about how identity, incentives, and technology shape society and markets.</em></p>

<p align="center">
I work at the edges of <strong>political economy</strong>, <strong>applied micro</strong>, and <strong>energy economy</strong>.
</p>

<p align="center">Vancouver, BC · ✉️ <a href="mailto:eizadi@sfu.ca">eizadi@sfu.ca</a></p>


<hr style="margin:1rem 0 1.2rem; border:0; border-top:1px solid rgba(0,0,0,.08)">

<style>
  .latest-list{list-style:none; margin:.2rem 0 0; padding:0}
  .latest-list li{padding:.45rem 0; border-top:1px solid rgba(0,0,0,.08)}
  .latest-list li:first-child{border-top:0}
  .latest-list a{text-decoration:none; border-bottom:1px solid rgba(0,0,0,.15)}
  .latest-list a:hover{border-color:rgba(0,0,0,.35)}
  .latest-list .meta{color:#777; font-size:.92rem}
</style>

### Latest from the blog

{% assign docs = site.blog | sort: "date" | reverse %}
<ul class="latest-list">
{% for post in docs limit:3 %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="meta"> — {{ post.date | date: "%b %-d, %Y" }}</span>
  </li>
{% endfor %}
</ul>

<p><a href="/blog/">View all notes →</a></p>

