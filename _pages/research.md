---
layout: single
title: "Research"
permalink: /research/
author_profile: false
classes: wide
---

{% assign papers = site.research | sort: "date" | reverse %}

<style>
  /* Minimal, quiet styling */
  .research-wrap{max-width:820px;margin:0 auto}
  .paper-list{list-style:none;margin:0;padding:0}
  .paper{padding:1rem 0;border-top:1px solid rgba(0,0,0,.08)}
  .paper:first-child{border-top:0}
  .paper-title{font-weight:600;text-decoration:none;color:inherit}
  .paper-title:hover{opacity:.85}
  .meta{display:block;margin-top:.15rem;color:#666;font-size:.95rem}
  .actions{margin-top:.6rem;display:flex;gap:.5rem}
  .btn{
    display:inline-block;
    border:1px solid rgba(0,0,0,.15);
    border-radius:999px;
    padding:.38rem .8rem;
    font-size:.92rem;
    text-decoration:none;
    line-height:1;
    color:inherit;                    /* <-- makes <a> match <button> */
    background:#4e5765;               /* <-- same fill for both */
  }
  .btn:hover{background:#eef0f3}
  a.btn:visited{color:inherit}
  .abstract{margin-top:.6rem;color:#333}
  .abstract[hidden]{display:none !important}
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
          <button
            type="button"
            class="btn soft js-abs-toggle"
            aria-controls="abs-{{ slug }}"
            aria-expanded="false"
            data-target="abs-{{ slug }}">
            Show abstract
          </button>
        {% endif %}
      </div>

      {% if abstract_text %}
        <div id="abs-{{ slug }}" class="abstract" hidden>
          {{ abstract_text | markdownify }}
        </div>
      {% endif %}
    </li>
  {% endfor %}
  </ul>
</div>

<script>
  // Minimal vanilla JS to toggle abstracts inline
  document.addEventListener('click', function(e){
    var btn = e.target.closest('.js-abs-toggle');
    if(!btn) return;
    var id = btn.getAttribute('data-target');
    var box = document.getElementById(id);
    if(!box) return;

    var isHidden = box.hasAttribute('hidden');
    if(isHidden){
      box.removeAttribute('hidden');
      btn.setAttribute('aria-expanded','true');
      btn.textContent = 'Hide abstract';
    }else{
      box.setAttribute('hidden','');
      btn.setAttribute('aria-expanded','false');
      btn.textContent = 'Show abstract';
    }
  }, false);
</script>
