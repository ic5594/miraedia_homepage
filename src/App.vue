<script setup>
/*
=========================================================
* Vue Material Kit 2 - v2.0.0
=========================================================

* Product Page: https://www.creative-tim.com/product/vue-material-kit
* Copyright 2022 Creative Tim (https://www.creative-tim.com)

Coded by www.creative-tim.com

 =========================================================

* The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
*/
import { RouterView } from "vue-router";
</script>

<template>
    <router-view />
</template>
<style>
#app {
  height: 100%;
}
html,
body {
  position: relative;
  height: 100%;
}
.swiper {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: #fff;

  /* Center slide text vertically */
  display: flex;
  justify-content: center;
  align-items: center;
}

.swiper-slide img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* font */
@font-face { 
  font-family: "NanumGothic";
  src: url("./assets/fonts/NanumGothic-Regular.ttf") format("truetype");
  font-weight: normal;
}

* {
    font-family: "NanumGothic" !important;
}

:root {
  --font-size-lg: 3rem;
  --font-size-md: 2rem;
  --font-size-sm: 1rem;
}

@media (min-width: 480px) {
  :root {
    --font-size-lg: 3rem;
    --font-size-md: 2rem;
    --font-size-sm: 1rem;

    --font-size-h1: 4.3rem;
    --font-size-h2: 3.3rem;
    --font-size-h3: 3rem;
    --font-size-h4: 2.5rem;
    --font-size-h5: 2rem;
  }
}

@media (min-width: 720px) {
  :root {
    --font-size-lg: 3.25rem;
    --font-size-md: 2.25rem;
    --font-size-sm: 1.25rem;

    --font-size-h1: 4.6rem;
    --font-size-h2: 3.6rem;
    --font-size-h3: 3rem; 
    --font-size-h4: 2.5rem;
    --font-size-h5: 2rem;
  }
}

@media (min-width: 1024px) {
  :root {
    --font-size-lg: 3.5rem;
    --font-size-md: 2.5rem;
    --font-size-sm: 1.5rem;

    --font-size-h1: 4.9rem;
    --font-size-h2: 3.9rem;
    --font-size-h3: 4rem;
    --font-size-h4: 3rem;
    --font-size-h5: 2rem;
  }
}

h1 {
    font-size: calc(1.425rem + 2.1vw)!important;
}

h2 {
    font-size: calc(1.35rem + 1.2vw) !important;
}

h3 {
    font-size: calc(1.3125rem + 0.75vw) !important;
}

h4 {
    font-size: calc(1.275rem + 0.3vw)!important;
}

h5 {
  font-size: var(--font-size-h5) !important;
}

p {
  font-size: var(--font-size-sm) !important;
}

a {
  font-size: var(--font-size-sm) !important;
}

blockquote {
  font-size: var(--font-size-md);
}

.hero {
  font-size: var(--font-size-lg);
}
</style>