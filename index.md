---
layout: single
title: ""
permalink: /
author_profile: false
classes: wide
---

<style>
:root{
  --bg-dim: rgba(0,0,0,.46);
  --ink: #f8faf9;
  --muted: rgba(248,250,249,.83);
  --accent: #cab28a;
  --btn-bg: rgba(34,26,16,.32);
  --btn-bg-hover: rgba(34,26,16,.5);
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
  grid-template-columns: clamp(260px, 26vw, 380px) 1fr clamp(160px, 16vw, 220px);
  gap: clamp(1rem, 2.6vw, 3rem);
}

/* ---------- Profile ---------- */
.hero__card{
  background: rgba(34,26,16,.24);
  border: 1px solid rgba(248,250,249,.26);
  border-radius: var(--radius);
  text-align:center;
  padding: 1rem;
  backdrop-filter: blur(6px);
}
.hero__card img{
  width: clamp(180px, 18vw, 260px);
  height: clamp(180px, 18vw, 260px);
  border-radius: 28%;
  object-fit: cover;
  object-position: 50% 20%;
  margin: .25rem 0 .8rem;
  border: 2px solid rgba(255,255,255,.08);
}
.hero__card .title{ font-weight: 800; font-size: 1.3rem; }
.hero__contact{ margin-top:.45rem; font-size: 1rem; color: var(--muted); }
.hero__contact a{ color: var(--ink); text-decoration:none; border-bottom:1px solid rgba(255,255,255,.4); }

/* ---------- Intro ---------- */
.hero__text{ max-width: 56ch; align-self: center; }
.hero__text p{
  font-size: 1.05rem;
  line-height: 1.6;
  margin: .35rem 0 1rem;
}
.hero__text strong{ color: var(--accent); }

/* ---------- Links (floating) ---------- */
.hero__links-vertical{
  display: flex;
  flex-direction: column;
  gap: .6rem;
  align-items: flex-end;
  justify-content: center;
}
.hero__links-vertical a{
  color: var(--ink);
  text-decoration: none;
  background: var(--btn-bg);
  border: 1px solid rgba(255, 255, 255, 0.35);
  border-radius: 999px;
  padding: .4rem .9rem;
  font-size: .95rem;
  transition: background .25s ease, transform .15s ease;
}
.hero__links-vertical a:hover{
  background: var(--btn-bg-hover);
  transform: translateY(-2px);
}

/* ---------- Responsive ---------- */
@media (max-width: 1024px){
  .hero__inner{ grid-template-columns: clamp(260px, 40vw, 360px) 1fr; }
  .hero__links-vertical{ grid-column: span 2; order:3; align-items: center; margin-top: 1rem; }
}
@media (max-width: 820px){
  .hero__inner{ grid-template-columns: 1fr; gap: 1rem; }
  .hero__text{ max-width: 70ch; }
  .hero__links-vertical{ order:3; }
}
/* HOMEPAGE-ONLY TRIMS */

/* 1) Fill the viewport so there’s no white band below */
.hero{
  min-height: 100vh;                /* was ~82vh; ensures full-height hero */
  display: flex;                    /* centers inner grid vertically */
  align-items: center;
}

/* 2) Remove extra gutters around the content area (theme defaults) */
.initial-content,
.page,
.page__inner-wrap,
.page__content{
  padding-top: 0 !important;
  padding-bottom: 0 !important;
  margin-top: 0 !important;
  margin-bottom: 0 !important;
}

/* 3) Hide the footer strip on the homepage */
.page__footer,
.page__footer-follow{
  display: none !important;
}

/* 4) If the theme adds a top spacer when masthead is hidden, neutralize it */
.masthead,
.masthead + .initial-content{
  margin-top: 0 !important;
}

</style>

<section class="hero">
  <div class="hero__inner">
    <!-- LEFT: profile -->
    <aside class="hero__card">
      <img src="/images/Izzy.jpg" alt="Esmaeil Izadi">
      <div class="title">Esmaeil Izadi</div>
      <div class="hero__contact">
  Vancouver, BC, Canada <a href="mailto:esmaeil_izadi@sfu.ca">esmaeil_izadi@sfu.ca</a><br>

  <!-- LinkedIn -->
  <a href="https://www.linkedin.com/in/esiz/" target="_blank" rel="noopener" aria-label="LinkedIn" style="margin-right: .5rem;">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 24 24" style="vertical-align: middle;">
      <path d="M19 0h-14c-2.761 0-5 2.239-5 
               5v14c0 2.761 2.239 5 5 5h14c2.762 
               0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 
               19h-3v-10h3v10zm-1.5-11.268c-.966 
               0-1.75-.784-1.75-1.75s.784-1.75 
               1.75-1.75 1.75.784 
               1.75 1.75-.784 1.75-1.75 1.75zm13.5 
               11.268h-3v-5.604c0-1.337-.027-3.059-1.865-3.059-1.865 
               0-2.151 1.459-2.151 2.964v5.699h-3v-10h2.879v1.367h.041c.401-.759 
               1.379-1.559 2.838-1.559 3.034 0 
               3.6 1.996 3.6 4.59v5.602z"/>
    </svg>
  </a>

  <!-- GitHub -->
  <a href="https://github.com/esizadi" target="_blank" rel="noopener" aria-label="GitHub">
    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" viewBox="0 0 24 24" style="vertical-align: middle;">
      <path d="M12 .297c-6.63 0-12 5.373-12 
               12 0 5.303 3.438 9.8 8.205 
               11.387.6.113.82-.258.82-.577 
               0-.285-.01-1.04-.015-2.04-3.338.726-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.757-1.333-1.757-1.089-.744.084-.729.084-.729 
               1.205.084 1.838 1.237 1.838 
               1.237 1.07 1.835 2.809 1.304 
               3.495.997.108-.776.418-1.305.762-1.605-2.665-.305-5.466-1.334-5.466-5.931 
               0-1.31.469-2.381 1.236-3.221-.124-.303-.536-1.524.117-3.176 
               0 0 1.008-.322 3.301 1.23.957-.266 
               1.983-.399 3.003-.404 1.02.005 
               2.047.138 3.006.404 2.291-1.552 
               3.297-1.23 3.297-1.23.655 1.652.243 
               2.873.119 3.176.77.84 1.235 1.911 
               1.235 3.221 0 4.609-2.804 5.624-5.475 
               5.921.43.372.823 1.102.823 2.222 
               0 1.606-.014 2.898-.014 3.293 
               0 .322.216.694.825.576C20.565 22.092 
               24 17.592 24 12.297c0-6.627-5.373-12-12-12"/>
    </svg>
  </a>
</div>


    </aside>

    <!-- CENTER: intro -->
    <div class="hero__text">
        <p>I’m a <strong>PhD economist</strong> from Simon Fraser University. My research sits at the intersection of analytical social science and applied economics, focusing on how political and economic elites shape <strong>markets</strong>, <strong>institutions</strong>, and <strong>policies</strong>.</p>


  <p>Methodologically, I use applied formal theory, structural modeling and applied econometrics. These tools help me frame questions rigorously, design policy-relevant analyses, and test policies with evidence-based approaches.</p>
    </div>

    <!-- RIGHT: floating links -->
    <nav class="hero__links-vertical" aria-label="Primary">
      <a href="/cv/">CV</a>
      <a href="/research/">Research</a>
      <a href="/teaching/">Teaching</a>
      <a href="/blog/">Blog</a>
      <a href="/fa/">یادداشت‌های فارسی</a>
    </nav>
  </div>
</section>
