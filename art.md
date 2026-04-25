---
layout: post
title: Art
description: Photos and paintings
image:
show_tile: true
nav-menu: true
weight: 2
---

A collection of photos and paintings from over the years. For best experience, either open images one-by-one in Gallery mode, or use the Carousel mode. :)

<style>
#art-toggle {
  display: flex;
  gap: 0.5rem;
  margin: 1.5rem 0 1rem;
}
#art-toggle button {
  padding: 0.45rem 1.4rem;
  border: 2px solid #9bf1ff;
  background: transparent;
  color: #9bf1ff;
  cursor: pointer;
  font-size: 0.85rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  border-radius: 2px;
  transition: background 0.2s, color 0.2s;
}
#art-toggle button.active {
  background: #9bf1ff;
  color: #1b1f22;
}

/* --- Gallery --- */
#art-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 1rem;
}
.art-card {
  background: #242a2e;
  border-radius: 4px;
  overflow: hidden;
  cursor: pointer;
}
.art-card img {
  width: 100%;
  height: 300px;
  object-fit: contain;
  background: #242a2e;
  display: block;
  transition: opacity 0.2s;
}
.art-card:hover img { opacity: 0.8; }
.art-card-info {
  padding: 0.55rem 0.75rem 0.75rem;
}
.art-card-title {
  font-size: 0.9rem;
  font-weight: 600;
  color: #fff;
  margin: 0 0 0.2rem;
}
.art-card-caption {
  font-size: 0.78rem;
  color: #999;
  font-style: italic;
  margin: 0;
}

/* --- Carousel --- */
#art-carousel { text-align: center; }
#carousel-frame {
  max-width: 680px;
  margin: 0 auto;
}
#carousel-img {
  width: 100%;
  max-height: 500px;
  object-fit: contain;
  display: block;
  border-radius: 4px;
  opacity: 1;
  transition: opacity 0.5s ease;
}
#carousel-img.fading { opacity: 0; }
#carousel-info { margin-top: 0.9rem; }
#carousel-title {
  font-size: 1rem;
  font-weight: 600;
  color: #fff;
  margin: 0 0 0.25rem;
  opacity: 1;
  transition: opacity 0.5s ease;
}
#carousel-caption {
  font-size: 0.82rem;
  color: #999;
  font-style: italic;
  margin: 0;
  opacity: 1;
  transition: opacity 0.5s ease;
}
#carousel-title.fading,
#carousel-caption.fading { opacity: 0; }
#carousel-controls {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.2rem;
  margin-top: 1rem;
}
.carousel-btn {
  background: transparent;
  border: 2px solid #9bf1ff;
  color: #9bf1ff;
  width: 2.4rem;
  height: 2.4rem;
  font-size: 1.1rem;
  border-radius: 2px;
  cursor: pointer;
  transition: background 0.2s, color 0.2s;
  line-height: 1;
}
.carousel-btn:hover {
  background: #9bf1ff;
  color: #1b1f22;
}
#carousel-counter { font-size: 0.82rem; color: #888; min-width: 50px; }

/* --- Lightbox --- */
#art-lightbox {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.9);
  z-index: 9999;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
}
#lightbox-close {
  position: fixed;
  top: 1rem;
  right: 1.5rem;
  font-size: 2rem;
  color: #fff;
  cursor: pointer;
  background: none;
  border: none;
  line-height: 1;
  opacity: 0.65;
  transition: opacity 0.15s;
}
#lightbox-close:hover { opacity: 1; }
#lightbox-img {
  max-width: 88vw;
  max-height: 75vh;
  object-fit: contain;
  border-radius: 4px;
  display: block;
}
#lightbox-info { margin-top: 0.9rem; text-align: center; }
#lightbox-title {
  font-size: 1rem;
  font-weight: 600;
  color: #fff;
  margin: 0 0 0.25rem;
}
#lightbox-caption {
  font-size: 0.82rem;
  color: #aaa;
  font-style: italic;
  margin: 0;
}
</style>

<div id="art-toggle">
  <button id="btn-gallery" class="active">Gallery</button>
  <button id="btn-carousel">Carousel</button>
</div>

<div id="art-gallery"></div>

<div id="art-carousel" style="display:none;">
  <div id="carousel-frame">
    <img id="carousel-img" src="" alt="" />
  </div>
  <div id="carousel-info">
    <p id="carousel-title"></p>
    <p id="carousel-caption"></p>
  </div>
  <div id="carousel-controls">
    <button class="carousel-btn" id="carousel-prev">&#8592;</button>
    <span id="carousel-counter"></span>
    <button class="carousel-btn" id="carousel-next">&#8594;</button>
  </div>
</div>

<div id="art-lightbox" style="display:none;">
  <button id="lightbox-close">&times;</button>
  <img id="lightbox-img" src="" alt="" />
  <div id="lightbox-info">
    <p id="lightbox-title"></p>
    <p id="lightbox-caption"></p>
  </div>
</div>

<script>
const artPieces = [
  { src: "{{ site.baseurl }}/assets/images/IMG_20230409_175130_014.jpg",   title: "Sunset at Bass Harbor", caption: "Acrylic on Canvas, 3in x 3in." },
  { src: "{{ site.baseurl }}/assets/images/IMG_20240705_125344_011.jpg",   title: "A classic childhood subject, revisited", caption: "Acrylic on Canvas, 3in x 3in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20230606_004441195.jpg",    title: "Sophie, lounging", caption: "Acrylic on Canvas, 9in. x 9 in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20250323_202326353.MP.jpg", title: "Sunset at Bass Harbor", caption: "Acrylic on Canvas, 9in. x 9in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20250502_023949908~2.jpg",  title: "Four Seasons", caption: "Mixed media on Canvas, 8in. x 10in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20250511_015550017~2.jpg",  title: "A quiet sunset", caption: "Acrylic on Canvas, 8in. x 10in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20250521_225906006.jpg",    title: "Philly Spring", caption: "Acrylic on Canvas, 8in. x 10in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20250521_230156498.jpg",    title: "When life gives you lemons, paint them", caption: "Acrylic on Canvas, 8in. x 10in." },
  { src: "{{ site.baseurl }}/assets/images/PXL_20251130_184623018.jpg",    title: "Fall at the Japanese Garden", caption: "Acrylic on Canvas, 8in. x 10in." },
  { src: "{{ site.baseurl }}/assets/images/IMG_20190902_193525.jpg",       title: "Art 10",  caption: "Caption 10" },
  { src: "{{ site.baseurl }}/assets/images/IMG_20200416_190539.jpg",       title: "Art 11",  caption: "Caption 11" },
  { src: "{{ site.baseurl }}/assets/images/IMG_20231023_173825_482.jpg",   title: "Art 12",  caption: "Caption 12" },
  { src: "{{ site.baseurl }}/assets/images/IMG_20240324_090912_101.jpg",   title: "Art 13",  caption: "Caption 13" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20201115_191213802.jpg",    title: "Art 14",  caption: "Caption 14" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20210110_194939121.jpg",    title: "Art 15",  caption: "Caption 15" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20210515_160411983.jpg",    title: "Art 16",  caption: "Caption 16" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20210806_231817076.jpg",    title: "Art 17",  caption: "Caption 17" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20210923_215410086.jpg",    title: "Art 18",  caption: "Caption 18" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20220509_071601463~2.jpg",  title: "Art 19",  caption: "Caption 19" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20220527_111921669~2.jpg",  title: "Art 20",  caption: "Caption 20" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20220629_213149584.jpg",    title: "Art 21",  caption: "Caption 21" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20220828_012044388.jpg",    title: "Art 22",  caption: "Caption 22" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20221020_005658711.jpg",    title: "Art 23",  caption: "Caption 23" },
  { src: "{{ site.baseurl }}/assets/images/PXL_20260119_204650477.jpg",    title: "Art 24",  caption: "Caption 24" },
  { src: "{{ site.baseurl }}/assets/images/PicsArt_12-14-08.39.43.jpg",   title: "Art 25",  caption: "Caption 25" },
];

/* ---- Gallery ---- */
const galleryEl = document.getElementById('art-gallery');
artPieces.forEach((p, i) => {
  const card = document.createElement('div');
  card.className = 'art-card';
  card.innerHTML =
    '<img src="' + p.src + '" alt="' + p.title + '" loading="lazy" />' +
    '<div class="art-card-info">' +
      '<p class="art-card-title">' + p.title + '</p>' +
      '<p class="art-card-caption">' + p.caption + '</p>' +
    '</div>';
  card.addEventListener('click', () => openLightbox(i));
  galleryEl.appendChild(card);
});

/* ---- Mode toggle ---- */
document.getElementById('btn-gallery').addEventListener('click', () => setMode('gallery'));
document.getElementById('btn-carousel').addEventListener('click', () => setMode('carousel'));

function setMode(mode) {
  const isGallery = mode === 'gallery';
  galleryEl.style.display = isGallery ? 'grid' : 'none';
  document.getElementById('art-carousel').style.display = isGallery ? 'none' : 'block';
  document.getElementById('btn-gallery').classList.toggle('active', isGallery);
  document.getElementById('btn-carousel').classList.toggle('active', !isGallery);
  isGallery ? stopCarousel() : startCarousel();
}

/* ---- Lightbox ---- */
function openLightbox(i) {
  const p = artPieces[i];
  document.getElementById('lightbox-img').src = p.src;
  document.getElementById('lightbox-img').alt = p.title;
  document.getElementById('lightbox-title').textContent = p.title;
  document.getElementById('lightbox-caption').textContent = p.caption;
  document.getElementById('art-lightbox').style.display = 'flex';
  document.body.style.overflow = 'hidden';
}

function closeLightbox() {
  document.getElementById('art-lightbox').style.display = 'none';
  document.body.style.overflow = '';
}

document.getElementById('art-lightbox').addEventListener('click', function(e) {
  if (e.target === this) closeLightbox();
});
document.getElementById('lightbox-close').addEventListener('click', closeLightbox);
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') closeLightbox();
});

/* ---- Carousel ---- */
let carouselIndex = 0;
let carouselTimer = null;
const FADE_MS = 500;
const INTERVAL_MS = 5000;

function showSlide(i, animate) {
  const p = artPieces[i];
  const img    = document.getElementById('carousel-img');
  const title  = document.getElementById('carousel-title');
  const caption = document.getElementById('carousel-caption');

  function swap() {
    img.src = p.src;
    img.alt = p.title;
    title.textContent = p.title;
    caption.textContent = p.caption;
    document.getElementById('carousel-counter').textContent = (i + 1) + ' / ' + artPieces.length;
  }

  if (animate) {
    img.classList.add('fading');
    title.classList.add('fading');
    caption.classList.add('fading');
    setTimeout(function() {
      swap();
      img.classList.remove('fading');
      title.classList.remove('fading');
      caption.classList.remove('fading');
    }, FADE_MS);
  } else {
    swap();
  }
}

function startCarousel() {
  showSlide(carouselIndex, false);
  carouselTimer = setInterval(function() {
    carouselIndex = (carouselIndex + 1) % artPieces.length;
    showSlide(carouselIndex, true);
  }, INTERVAL_MS);
}

function stopCarousel() {
  clearInterval(carouselTimer);
  carouselTimer = null;
}

function step(dir) {
  carouselIndex = (carouselIndex + dir + artPieces.length) % artPieces.length;
  showSlide(carouselIndex, true);
  stopCarousel();
  carouselTimer = setInterval(function() {
    carouselIndex = (carouselIndex + 1) % artPieces.length;
    showSlide(carouselIndex, true);
  }, INTERVAL_MS);
}

document.getElementById('carousel-prev').addEventListener('click', () => step(-1));
document.getElementById('carousel-next').addEventListener('click', () => step(1));
document.addEventListener('keydown', function(e) {
  if (document.getElementById('art-carousel').style.display === 'none') return;
  if (e.key === 'ArrowLeft')  step(-1);
  if (e.key === 'ArrowRight') step(1);
});
</script>
