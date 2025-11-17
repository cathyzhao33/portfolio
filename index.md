---
layout: default
title: "Cathy Zhao"
---

<style>
/* Page tweaks */
h1, h2 {
  margin-top: 1.5rem;
}
.resume-button {
  display: inline-block;
  padding: 0.5rem 1rem;
  border: 1px solid #555;
  border-radius: 4px;
  text-decoration: none;
}
.resume-button:hover {
  background: #f5f5f5;
}

/* Gallery grid */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1.5rem;
  margin-top: 1rem;
}
.gallery figure {
  margin: 0;
}
.gallery img {
  width: 100%;
  height: auto;
  border-radius: 6px;
}
.gallery figcaption {
  font-size: 0.9rem;
  margin-top: 0.4rem;
}
</style>

# Cathy Zhao

Welcome to my portfolio site.

---

## Resume

[Download my resume](./resume.pdf){: .resume-button }

---

## Gallery {#gallery}

<!-- SLIDESHOW -->
<style>
.slideshow-container {
  max-width: 700px;
  margin: 1.5rem auto;
  position: relative;
}

.slide {
  display: none;
}

.slide img {
  width: 100%;
  border-radius: 6px;
}

.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 12px;
  margin-top: -22px;
  color: #333;
  font-weight: bold;
  font-size: 18px;
  border-radius: 0 3px 3px 0;
  user-select: none;
  background: rgba(255, 255, 255, 0.7);
}

.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

.prev:hover, .next:hover {
  background-color: rgba(255, 255, 255, 0.95);
}

.caption {
  text-align: center;
  font-size: 0.9rem;
  padding: 8px;
  color: #444;
}
</style>

<div class="slideshow-container">

  <!-- 1 -->
  <div class="slide">
    <img src="assets/img/IMG_2794.JPG">
    <div class="caption">Lights on Lake Union from my hometown, Seattle, Washington.</div>
  </div>

  <!-- 2 -->
  <div class="slide">
    <img src="assets/img/IMG_3860.JPG">
    <div class="caption">Cherry blossoms at the University of Washington.</div>
  </div>

  <!-- 3 -->
  <div class="slide">
    <img src="assets/img/IMG_1847.JPG">
    <div class="caption">First time going to Apple Fest in Ithaca.</div>
  </div>

  <!-- 4 -->
  <div class="slide">
    <img src="assets/img/IMG_3226.JPG">
    <div class="caption">Viewing the night sky at Cornell’s Fuertes Observatory.</div>
  </div>

  <!-- 5 -->
  <div class="slide">
    <img src="assets/img/IMG_5800.JPG">
    <div class="caption">Trying real Texas BBQ in Austin.</div>
  </div>

  <!-- 6 -->
  <div class="slide">
    <img src="assets/img/IMG_7682.JPG">
    <div class="caption">Free lunch from leftover conference catering.</div>
  </div>

  <!-- 7 -->
  <div class="slide">
    <img src="assets/img/IMG_6239.JPG">
    <div class="caption">Dessert from my favorite restaurant during my internship.</div>
  </div>

  <!-- 8 -->
  <div class="slide">
    <img src="assets/img/IMG_7380.JPG">
    <div class="caption">Le Chat Blanc at the Musée d’Orsay.</div>
  </div>

  <!-- Buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>

</div>

<script>
let slideIndex = 1;
let autoTimer = null;

showSlides(slideIndex);
startAutoSlide();

function plusSlides(n) {
  showSlides(slideIndex += n);
  resetAutoSlide();
}

function showSlides(n) {
  let i;
  let slides = document.getElementsByClassName("slide");
  if (n > slides.length) { slideIndex = 1 }
  if (n < 1) { slideIndex = slides.length }

  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }

  slides[slideIndex - 1].style.display = "block";
}

function startAutoSlide() {
  autoTimer = setInterval(() => {
    showSlides(++slideIndex);
  }, 5000); // 5 seconds per slide
}

function resetAutoSlide() {
  clearInterval(autoTimer);
  startAutoSlide();
}
</script>


