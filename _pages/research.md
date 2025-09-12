---
layout: single
title: "Research"
permalink: /research/
author_profile: false
classes: wide
---

{% assign papers = site.research | sort: "date" | reverse %}

<style>
  .research-wrap{max-width:820px;margin:0 auto}
  .paper-list{list-style:none;margin:0;padding:0}
  .paper{padding:1rem 0;border-top:1px solid rgba(0,0,0,.08)}
  .paper:first-child{border-top:0}
  .paper-title{font-weight:600;text-decoration:none;color:inherit}
  .paper-title:hover{opacity:.85}
  .meta{display:block;margin-top:.15rem;color:#666;font-size:.95rem}

  /* Buttons — slightly lighter */
  .btn{
    display:inline-block;
    border:1px solid rgba(0,0,0,.15);
    border-radius:999px;
    padding:.38rem .8rem;
    font-size:.92rem;
    text-decoration:none;
    line-height:1;
    color:#fff;
    background:#7a8390;   /* lighter than #546c63ff */
    cursor:pointer;
  }
  .btn:hover{ filter:brightness(1.05); }
  a.btn:visited{ color:#fff; }

  .actions{
    margin-top:.6rem;
    display:flex;
    gap:.5rem;
    align-items:center;
    flex-wrap:wrap;
  }

  .abs-block > summary{ list-style:none; cursor:pointer; }
  .abs-block > summary::-webkit-details-marker{ display:none; }
  .abs-block > summary.btn{ display:inline-block; }

  .abs-block > summary .when-open{ display:none; }
  .abs-block[open] > summary .when-closed{ display:none; }
  .abs-block[open] > summary .when-open{ display:inline; }

  .paper .abstract{ display:none; margin-top:.6rem; color:#333; }
  .actions:has(details[open]) + .abstract{ display:block; }
</style>

<div class="research-wrap">
  <ul class="paper-list">
  {% for p in papers %}
    {% assign slug = p.title | slugify %}
    {% assign abstract_text = p.abstract | default: p.excerpt %}
    <li class="paper">
      <a class="paper-title" href="{{ p.url | relative_url }}">{{ p.title }}</a>
      <span class="meta">
        {% if p.status or p.year %}
          {% if p.status %}{{ p.status }}{% endif %}
          {% if p.year %}{% if p.status %} · {% endif %}{{ p.year }}{% endif %}
        {% endif %}
        {% if p.coauthors %} · with {{ p.coauthors }}{% endif %}
      </span>

      <div class="actions">
        {% if p.pdf %}
          <a class="btn" href="{{ p.pdf | relative_url }}" target="_blank" rel="noopener">Full text (PDF)</a>
        {% endif %}
        {% if abstract_text %}
          <details class="abs-block">
            <summary class="btn">
              <span class="when-closed">Show abstract</span>
              <span class="when-open">Hide abstract</span>
            </summary>
          </details>
        {% endif %}
      </div>

      {% if abstract_text %}
        <div class="abstract">
          {{ abstract_text | markdownify }}
        </div>
      {% endif %}
    </li>
  {% endfor %}
  </ul>
</div>
