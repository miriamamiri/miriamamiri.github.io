---
title: "Photography"
layout: default
permalink: /photography/
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/lightgallery@2.8.2/css/lightgallery-bundle.min.css">
<link rel="stylesheet" href="{{ '/assets/css/photography.css' | relative_url }}">

<div class="hero-slider">
  <div class="section-title">Featured</div>
  <div class="swiper">
    <div class="swiper-wrapper">
      <!-- Replace sample images with yours -->
      <div class="swiper-slide">
        <img src="{{ '/assets/photography/full/esiz.JPG' | relative_url }}" alt="Featured photo 1">
      </div>
      <div class="swiper-slide">
        <img src="{{ '/assets/photography/full/office.jpeg' | relative_url }}" alt="Featured photo 2">
      </div>
      <div class="swiper-slide">
        <img src="{{ '/assets/photography/full/hero.jpg' | relative_url }}" alt="Featured photo 3">
      </div>
    </div>
    <!-- Nav -->
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
    <!-- Pagination -->
    <div class="swiper-pagination"></div>
  </div>
</div>

<div class="gallery-wrap">
  <div class="section-title">Gallery</div>
  <p class="subtle">Click any image to open the lightbox.</p>

  <!-- LightGallery target -->
  <div id="lightgallery" class="gallery-grid">
    <!-- Each anchor: data-src points to large file, <img> shows the thumbnail -->
    <a href="#" data-src="{{ '/assets/photography/full/001.jpg' | relative_url }}" data-sub-html="Caption one">
      <img src="{{ '/assets/photography/thumbs/001.jpg' | relative_url }}" alt="Photo 1">
    </a>
    <a href="#" data-src="{{ '/assets/photography/full/002.jpg' | relative_url }}" data-sub-html="Caption two">
      <img src="{{ '/assets/photography/thumbs/002.jpg' | relative_url }}" alt="Photo 2">
    </a>
    <a href="#" data-src="{{ '/assets/photography/full/003.jpg' | relative_url }}" data-sub-html="Caption three">
      <img src="{{ '/assets/photography/thumbs/003.jpg' | relative_url }}" alt="Photo 3">
    </a>
    <!-- Add more blocks as you add photos -->
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.8.2/lightgallery.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.8.2/plugins/thumbnail/lg-thumbnail.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/lightgallery@2.8.2/plugins/zoom/lg-zoom.min.js"></script>

<script>
  // Slider
  const swiper = new Swiper('.swiper', {
    loop: true,
    speed: 500,
    grabCursor: true,
    pagination: { el: '.swiper-pagination', clickable: true },
    navigation: { nextEl: '.swiper-button-next', prevEl: '.swiper-button-prev' },
  });

  // Lightbox
  lightGallery(document.getElementById('lightgallery'), {
    selector: 'a',
    download: false,
    thumbnail: true,
    zoom: true,
    mobileFirst: true,
    actualSize: false
  });
</script>
