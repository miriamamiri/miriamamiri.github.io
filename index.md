---
layout: single
title: ""
permalink: /
author_profile: false
classes: wide
---

{% comment %}
FAST featured-post resolver: search posts + 'blog' collection if present.
Resolve by URL → path → slug; fallback to first with featured:true.
{% endcomment %}
{% assign _featured = nil %}
{% assign _cands = site.posts %}
{% if site.blog %}{% assign _cands = _cands | concat: site.blog %}{% endif %}
{% if page.featured_post %}
  {% assign _featured = _cands | where: "url", page.featured_post | first %}
  {% if _featured == nil %}{% assign _featured = _cands | where: "path", page.featured_post | first %}{% endif %}
  {% if _featured == nil %}{% assign _featured = _cands | where: "slug", page.featured_post | first %}{% endif %}
{% endif %}
{% if _featured == nil %}
  {% assign _featured = _cands | where: "featured", true | first %}
{% endif %}

<style>
/* ---------- Palette & type ---------- */
:root{
  --bg-dim: rgba(0,0,0,.46);        /* darker overlay */
  --overlay: rgba(34,26,16,.24);    /* cards/buttons with more presence */
  --overlay-strong: rgba(34,26,16,.36);
  --ink: #f8faf9;
  --muted: rgba(248,250,249,.83);
  --ring: rgba(248,250,249,.26);
  --accent: #cab28a;
  --accent-2: #88b3a6;
  --accent-3: #c48787;
  --btn-bg: rgba(34,26,16,.24);
  --btn-bg-hover: rgba(34,26,16,.36);
  --radius: 18px;
}




html, body { overflow-x: hidden; }
.masthead{ display:none !important; }

/* ---------- Hero ---------- */
.hero{
  color: var(--ink);
  background:
    linear-gradient(0deg, var(--bg-dim), var(--bg-dim)),
    url('/images/Mamasani-tower-Eugène-Flandin.jpg') center 100%/cover no-repeat;
  min-height: clamp(520px, 82vh, 900px);
  margin-left: calc(50% - 50vw);
  width: 100vw;
}

.hero__inner{
  width: min(1200px, 94vw);
  margin: 0 auto;
  padding: clamp(1.2rem, 3.2vw, 3rem) clamp(1rem, 3vw, 2rem);
  display: grid;
  grid-template-columns: clamp(260px, 26vw, 380px) 1fr clamp(260px, 24vw, 360px);
  gap: clamp(1rem, 2.6vw, 3rem);
}

/* ---------- Shared card look ---------- */
.card{
  background: var(--overlay);
  border: 1px solid var(--ring);
  border-radius: var(--radius);
  backdrop-filter: blur(6px);
  box-shadow:
    0 12px 28px rgba(0,0,0,.28),
    inset 0 1px 0 rgba(255,255,255,.06);
}

/* ---------- Left: profile ---------- */
.hero__card{ padding: clamp(.9rem, 1.5vw, 1.1rem); text-align:center; }
.hero__card img{
  width: clamp(180px, 18vw, 260px);
  height: clamp(180px, 18vw, 260px);
  border-radius: 28%;
  object-fit: cover;
  object-position: 50% 20%;
  box-shadow: 0 6px 18px rgba(0,0,0,.35);
  margin: .25rem 0 .8rem;
  border: 2px solid rgba(255,255,255,.08);
}
.hero__card .title{
  font-weight: 800;
  font-size: clamp(1.15rem, 2.2vw, 1.6rem);
  letter-spacing: .2px;
}
.hero__contact{ margin-top:.45rem; font-size: 1.02rem; color: var(--muted); }
.hero__contact a{ color: var(--ink); text-decoration:none; border-bottom:1px solid rgba(255,255,255,.4); }

/* ---------- Center: lean intro ---------- */
.hero__text{ max-width: 56ch; text-wrap: balance; }
.hero__text p{
  font-size: clamp(1rem, 1.05vw, 1.12rem);
  line-height: 1.6;
  margin: .35rem 0 1rem;
}
.hero__text strong{
  color: var(--accent);   /* same color as .feature__eyebrow */
  background: none;
}


/* ---------- Buttons ---------- */
.hero__links{ margin-top:.6rem; display:flex; flex-wrap:wrap; gap:.5rem }
.hero__links a{
  color: var(--ink);
  text-decoration:none;
  background: var(--btn-bg);
  border: 1px solid rgba(255,255,255,.35);
  border-radius: 999px;
  padding: .36rem .72rem;
  font-size: .95rem;
  transition: background .24s ease, transform .12s ease;
}
.hero__links a:hover{ background: var(--btn-bg-hover); transform: translateY(-1px); }
.hero__links a:nth-child(1){ border-color: rgba(202,178,138,.55); }
.hero__links a:nth-child(2){ border-color: rgba(136,179,166,.55); }
.hero__links a:nth-child(3){ border-color: rgba(196,135,135,.55); }
.hero__links a:nth-child(4){ border-color: rgba(202,178,138,.55); }
.hero__links a:nth-child(5){ border-color: rgba(136,179,166,.55); }

/* ---------- Right: featured ---------- */
.feature{ padding: clamp(.9rem, 1.5vw, 1.1rem); }
.feature__eyebrow{
  letter-spacing:.08em; text-transform:uppercase; font-size:.78rem; opacity:.9;
  color: var(--accent);
}
.feature__thumb{
  width:100%; aspect-ratio:16/9; border-radius:12px; object-fit:cover;
  border:1px solid var(--ring); margin-top:.25rem;
}
.feature__title{ font-weight:800; font-size:clamp(1.05rem, 1.3vw, 1.22rem); line-height:1.34; margin:.3rem 0; }
.feature__title a{ color:var(--ink); text-decoration:none; border-bottom:1px solid transparent; }
.feature__title a:hover{ border-bottom-color: rgba(255,255,255,.5); }
.feature__meta{ font-size:.92rem; color:var(--muted); }
.feature__excerpt{ font-size:1rem; line-height:1.58; color:var(--ink); opacity:.96; }
.feature__cta{
  margin-top:auto;
  display:inline-block;
  text-align:center;
  color:#fff;
  background: var(--btn-bg);                 /* same as middle links */
  border:1px solid rgba(255,255,255,.35);    /* same border */
  border-radius:999px;
  padding:.4rem .8rem;
  font-size:.95rem;
  font-weight:500;
  text-decoration:none;
  transition: background .24s ease, transform .12s ease;
}
.feature__cta:hover{
  background: var(--btn-bg-hover);           /* same hover behavior */
  transform: translateY(-1px);
}



/* ---------- Subtle accents on cards ---------- */
.hero__card::after, .feature::after{
  content:""; display:block; height:3px; width:44%;
  background: linear-gradient(90deg, var(--accent), var(--accent-3));
  border-radius: 999px; opacity:.35; margin:.6rem auto 0;
}

/* ---------- Responsive ---------- */
@media (max-width: 1024px){
  .hero__inner{ grid-template-columns: clamp(260px, 40vw, 360px) 1fr; }
  .feature{ grid-column: span 2; order:3; }
}
@media (max-width: 820px){
  .hero__inner{ grid-template-columns: 1fr; gap: 1rem; }
  .hero__text{ max-width: 70ch; }
  .feature{ order:3; }
}
@media (max-width: 640px){
  .hero__text p:nth-of-type(2){ display:none; } /* ultra-lean on small screens */
}
</style>

<section class="hero">
  <div class="hero__inner">
    <!-- LEFT: profile -->
    <aside class="hero__card card">
      <img src="/images/Izzy.jpg" alt="Esmaeil Izadi">
      <div class="title">Call me Esmaeil!</div>
      <div class="hero__contact">
        Vancouver, BC · ✉️ <a href="mailto:esmaeil_izadi@sfu.ca">esmaeil_izadi@sfu.ca</a>
      </div>
    </aside>

    <!-- CENTER: crisp intro + links -->
    <div class="hero__text">
      <p><strong>Economist</strong> focused on political economy, firm networks, and the energy transition.</p>
      <p>I study how elites shape markets and institutions using <strong>applied micro</strong> theory and econometrics.</p>

      <nav class="hero__links">
        <a href="/cv/">CV</a>
        <a href="/research/">Research</a>
        <a href="/teaching/">Teaching</a>
        <a href="/blog/">Blog</a>
        <a href="/fa/">یادداشت‌های فارسی</a>
      </nav>
    </div>

    <!-- RIGHT: featured post -->
    {% if _featured %}
    <aside class="feature card" aria-labelledby="featured-post-heading">
      <div class="feature__eyebrow" id="featured-post-heading">Featured post</div>

      {% if _featured.image %}
        <a href="{{ _featured.url | relative_url }}">
          <img class="feature__thumb" src="{{ _featured.image | relative_url }}" alt="">
        </a>
      {% endif %}

      <h3 class="feature__title">
        <a href="{{ _featured.url | relative_url }}">{{ _featured.title }}</a>
      </h3>

      <div class="feature__meta">
        {{ _featured.date | date: "%B %-d, %Y" }}
      </div>

      <div class="feature__excerpt">
        {% if _featured.excerpt %}
          {{ _featured.excerpt | strip_html | strip_newlines | truncate: 220 }}
        {% else %}
          {{ _featured.content | strip_html | strip_newlines | truncate: 220 }}
        {% endif %}
      </div>

      <a class="feature__cta" href="{{ _featured.url | relative_url }}">Read the post</a>
    </aside>
    {% endif %}
  </div>
</section>
