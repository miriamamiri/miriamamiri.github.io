---
layout: single
title: ""            # no page H1; hero owns the page
permalink: /
author_profile: false
classes: wide
---

<style>
  /* Hide the masthead only on this page */
  .masthead{ display:none !important; }

  /* Full-bleed hero */
  .hero{
    background:
      linear-gradient(0deg, rgba(0,0,0,.46), rgba(0,0,0,.46)),
      url('/images/hero-lashayi.jpg') center 30%/cover no-repeat; /* change path if needed */
    min-height: clamp(520px, 82vh, 900px);
    margin-left: calc(50% - 50vw);
    width: 100vw;
    border-radius: 0;
    margin-bottom: 0;
  }
  html, body { overflow-x: hidden; } /* prevent horiz scrollbars */

  /* Fluid grid */
  .hero__inner{
    width: min(1200px, 94vw);
    margin: 0 auto;
    padding: clamp(1.2rem, 3.2vw, 3rem) clamp(1rem, 3vw, 2rem);
    display: grid;
    grid-template-columns: clamp(260px, 26vw, 380px) 1fr; /* left grows with screen */
    gap: clamp(1rem, 2.6vw, 3rem);
    color:#fff;
  }

  /* Left card */
  .hero__card{
    background: rgba(0,0,0,.25);
    border:1px solid rgba(255,255,255,.18);
    border-radius:14px;
    padding: clamp(.9rem, 1.5vw, 1.1rem);
    text-align:center;
    backdrop-filter: blur(4px);
  }
  .hero__card img{
    width: clamp(180px, 18vw, 260px);  /* larger portrait */
    height: clamp(180px, 18vw, 260px);
    border-radius:40%;
    object-fit:cover;
    box-shadow:0 6px 18px rgba(0,0,0,.35);
    margin:.25rem 0 .6rem;
  }
  .hero__card .lead {
    font-size: clamp(0.8rem, 2vw, 1.3rem);
    margin-bottom: 0.4rem;
  }
  .hero__contact a{
    color:#fff; text-decoration:none; border-bottom:1px solid rgba(255,255,255,.55);
  }

  /* Right text */
  .hero__text{ max-width: 62ch; }
  .hero__text .lead{
    font-size: clamp(1.25rem, 2.4vw, 1.7rem);  /* slightly larger than body */
    line-height: 1.65;
    margin: 2rem 0;
  }
  .hero__text p{
    font-size: clamp(1rem, 1.08vw, 1.12rem);
    line-height: 1.65;
    margin:.2rem 0;
  }

  /* Minimal links row */
  .hero__links{ margin-top:.9rem; display:flex; flex-wrap:wrap; gap:.5rem }
  .hero__links a{
    color:#fff; text-decoration:none;
    border:1px solid rgba(255,255,255,.45);
    border-radius:999px; padding:.4rem .75rem; font-size:.95rem;
  }
  .hero__links a:hover{ background: rgba(255, 255, 255, 0.33); }

  /* Mobile */
  @media (max-width: 820px){
    .hero__inner{ grid-template-columns: 1fr; gap: 1rem; }
    .hero__text{ max-width: 70ch; }
  }
</style>

<section class="hero">
  <div class="hero__inner">
    <!-- LEFT: photo + contact -->
    <aside class="hero__card">
      <img src="/images/Esmaeil-web.jpg" alt="Esmaeil Izadi">
      <p class="lead"><strong>Call me Esmaeil!</strong></p> <!-- moved here -->
      <div class="hero__contact" style="margin-top:.35rem;">
        Vancouver, BC · ✉️ <a href="mailto:esmaeil_izadi@sfu.ca">esmaeil_izadi@sfu.ca</a>
      </div>
    </aside>

    <!-- RIGHT: minimal text + links -->
    <div class="hero__text">
      <p>I'm a <strong>job market candidate</strong> in economics at Simon Fraser University. </p>
      
      <p>My research interests include <strong>political economy</strong> of development, firm strategy and networks, and energy transition.</p>

      <p>The common theme in my work is how political and economic elites influence market and societal outcomes. I use <strong>applied micro</strong> theory and econometrics to explore questions.</p>

      <nav class="hero__links">
        <a href="/cv/">CV</a>
        <a href="/research/">Research</a>
        <a href="/blog/">Blog</a>
        <a href="/teaching/">Teaching</a>
        <a href="/fa/">یاداشت‌های فارسی</a>
      </nav>
    </div>
  </div>
</section>
