---
layout: single
title: "Research"
permalink: /research/
author_profile: false
classes: wide
---

{% assign papers = site.research | sort: "date" | reverse %}

{%- comment -%} Build a unique, sorted list of areas from all papers {%- endcomment -%}
{% assign areas_concat = "" %}
{% for p in papers %}
  {% if p.areas %}
    {% for a in p.areas %}
      {% assign areas_concat = areas_concat | append: a | append: "|" %}
    {% endfor %}
  {% endif %}
{% endfor %}
{% assign areas = areas_concat | split: "|" | uniq | sort %}

<style>
  .pillnav{display:flex;flex-wrap:wrap;gap:.4rem;margin:.25rem 0 1rem}
  .pillnav a{padding:.25rem .6rem;border:1px solid rgba(0,0,0,.15);border-radius:999px;text-decoration:none;color:inherit}
  .pillnav a.active,.pillnav a:hover{background:#f6f7f9;border-color:rgba(0,0,0,.25)}
  .paper-list{list-style:none;margin:.2rem 0 1.2rem 0;padding:0}
  .paper-item{padding:.6rem 0;border-top:1px solid rgba(0,0,0,.08)}
  .paper-item:first-child{border-top:0}
  .meta{color:#666;font-size:.95rem}
  .abs{margin:.35rem 0 .5rem;color:#333}
  .btn{display:inline-block;border:1px solid rgba(0,0,0,.15);border-radius:999px;padding:.3rem .65rem;font-size:.9rem;text-decoration:none;margin-right:.35rem}
  .btn.soft{background:#f6f7f9}
</style>

<!-- Areas (filters). Click to narrow the list below. -->
<nav class="pillnav">
  <a href="#all" data-filter="">All</a>
  {% for area in areas %}{% if area != "" %}
    <a href="#area-{{ area | slugify }}" data-filter="{{ area | slugify }}">{{ area }}</a>
  {% endif %}{% endfor %}
</nav>

<ul class="paper-list" id="paper-list">
{% for p in papers %}
  {%- comment -%} Build slug list for this paper's areas {%- endcomment -%}
  {% assign slugs = "" %}
  {% if p.areas %}
    {% for a in p.areas %}
      {% assign sa = a | slugify %}
      {% if forloop.first %}
        {% assign slugs = sa %}
      {% else %}
        {% assign slugs = slugs | append:"|" | append: sa %}
      {% endif %}
    {% endfor %}
  {% endif %}

  <li class="paper-item" data-areas="{{ slugs }}">
    <a href="{{ p.url | relative_url }}"><strong>{{ p.title }}</strong></a>
    {% if p.status or p.year %}<span class="meta"> — {% if p.status %}{{ p.status }}{% endif %}{% if p.year %}{% if p.status %} · {% endif %}{{ p.year }}{% endif %}</span>{% endif %}
    {% if p.coauthors %}<span class="meta"> · with {{ p.coauthors }}</span>{% endif %}
    {% if p.excerpt %}<div class="abs">{{ p.excerpt | strip_html | strip_newlines }}</div>{% endif %}
    <div class="links">
      {% if p.pdf %}<a class="btn" href="{{ p.pdf | relative_url }}">PDF</a>{% endif %}
      {% if p.slides %}<a class="btn soft" href="{{ p.slides | relative_url }}">Slides</a>{% endif %}
      {% if p.code %}<a class="btn soft" href="{{ p.code }}">Code</a>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>

<script>
(function(){
  function currentFilter(){
    if(location.hash && location.hash.indexOf('#area-')===0){
      return location.hash.replace('#area-','');
    }
    return "";
  }
  function applyFilter(slug){
    var items = document.querySelectorAll('.paper-item');
    items.forEach(function(el){
      var areas = (el.getAttribute('data-areas')||'').split('|').filter(Boolean);
      var show = !slug || areas.includes(slug);
      el.style.display = show ? "" : "none";
    });
    document.querySelectorAll('.pillnav a').forEach(function(a){
      a.classList.toggle('active', (a.getAttribute('data-filter')||"") === slug);
    });
  }
  // init + respond to hash changes
  applyFilter(currentFilter());
  window.addEventListener('hashchange', function(){ applyFilter(currentFilter()); });
})();
</script>
