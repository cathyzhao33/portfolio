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

/* Fade-in animation for active slide */
.slide.active {
  display: block;
  animation: fade 0.6s ease-in-out;
}

@keyframes fade {
  from { opacity: 0; }
  to   { opacity: 1; }
}

/* Dots / indicators */
.dots {
  text-align: center;
  margin-top: 0.75rem;
}

.dot {
  cursor: pointer;
  height: 10px;
  width: 10px;
  margin: 0 4px;
  border-radius: 50%;
  display: inline-block;
  border: 1px solid #666;
  background: #ddd;
  transition: background-color 0.3s, transform 0.3s;
}

.dot.active {
  background: #666;
  transform: scale(1.1);
}
</style>

<div class="slideshow-container">

  <!-- 1 -->
  <div class="slide">
    <img src="assets/img/IMG_2794.JPG" alt="Lights on Lake Union" />
    <div class="caption">Lights on Lake Union from my hometown, Seattle, Washington.</div>
  </div>

  <!-- 2 -->
  <div class="slide">
    <img src="assets/img/IMG_3860.JPG" alt="Cherry blossoms at UW" />
    <div class="caption">Cherry blossoms at the University of Washington.</div>
  </div>

  <!-- 3 -->
  <div class="slide">
    <img src="assets/img/IMG_1847.JPG" alt="Apple Fest in Ithaca" />
    <div class="caption">First time going to Apple Fest in Ithaca.</div>
  </div>

  <!-- 4 -->
  <div class="slide">
    <img src="assets/img/IMG_3226.JPG" alt="Fuertes Observatory" />
    <div class="caption">Viewing the night sky at Cornell’s Fuertes Observatory.</div>
  </div>

  <!-- 5 -->
  <div class="slide">
    <img src="assets/img/IMG_5800.JPG" alt="Texas BBQ" />
    <div class="caption">Trying real Texas BBQ in Austin.</div>
  </div>

  <!-- 6 -->
  <div class="slide">
    <img src="assets/img/IMG_7682.JPG" alt="Free lunch at work" />
    <div class="caption">Free lunch from leftover conference catering.</div>
  </div>

  <!-- 7 -->
  <div class="slide">
    <img src="assets/img/IMG_6239.JPG" alt="Dessert in Austin" />
    <div class="caption">Dessert from my favorite restaurant during my internship.</div>
  </div>

  <!-- 8 -->
  <div class="slide">
    <img src="assets/img/IMG_7380.JPG" alt="Le Chat Blanc" />
    <div class="caption">Le Chat Blanc at the Musée d’Orsay.</div>
  </div>

  <!-- Buttons -->
  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>

</div>

<!-- Slide indicators -->
<div class="dots">
  <span class="dot" onclick="currentSlide(1)"></span>
  <span class="dot" onclick="currentSlide(2)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
  <span class="dot" onclick="currentSlide(4)"></span>
  <span class="dot" onclick="currentSlide(5)"></span>
  <span class="dot" onclick="currentSlide(6)"></span>
  <span class="dot" onclick="currentSlide(7)"></span>
  <span class="dot" onclick="currentSlide(8)"></span>
</div>

<script>
let slideIndex = 1;
let autoTimer = null;

const slides = document.getElementsByClassName("slide");
const dots = document.getElementsByClassName("dot");
const container = document.querySelector(".slideshow-container");

function showSlides(n) {
  if (!slides.length) return;

  if (n > slides.length) { slideIndex = 1; }
  if (n < 1) { slideIndex = slides.length; }

  // Clear all
  for (let i = 0; i < slides.length; i++) {
    slides[i].classList.remove("active");
  }
  for (let i = 0; i < dots.length; i++) {
    dots[i].classList.remove("active");
  }

  // Activate current
  slides[slideIndex - 1].classList.add("active");
  if (dots[slideIndex - 1]) {
    dots[slideIndex - 1].classList.add("active");
  }
}

function plusSlides(n) {
  slideIndex += n;
  showSlides(slideIndex);
  resetAutoSlide();
}

function currentSlide(n) {
  slideIndex = n;
  showSlides(slideIndex);
  resetAutoSlide();
}

function startAutoSlide() {
  autoTimer = setInterval(function() {
    slideIndex++;
    showSlides(slideIndex);
  }, 5000); // 5 seconds per slide
}

function resetAutoSlide() {
  clearInterval(autoTimer);
  startAutoSlide();
}

// Pause on hover
if (container) {
  container.addEventListener("mouseenter", function() {
    clearInterval(autoTimer);
  });

  container.addEventListener("mouseleave", function() {
    startAutoSlide();
  });

  // Swipe on mobile
  let touchStartX = null;

  container.addEventListener("touchstart", function(e) {
    touchStartX = e.changedTouches[0].screenX;
  }, { passive: true });

  container.addEventListener("touchend", function(e) {
    if (touchStartX === null) return;
    const touchEndX = e.changedTouches[0].screenX;
    const diffX = touchEndX - touchStartX;
    const threshold = 50; // px

    if (Math.abs(diffX) > threshold) {
      if (diffX < 0) {
        plusSlides(1);   // swipe left -> next
      } else {
        plusSlides(-1);  // swipe right -> prev
      }
    }
    touchStartX = null;
  }, { passive: true });
}

// Init
showSlides(slideIndex);
startAutoSlide();
</script>





