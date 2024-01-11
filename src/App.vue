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
  src: url("./assets/fonts/NanumGothic-Regular.tff") format("truetype");
  font-weight: normal;
}

* {
    font-family: "NanumGothic" !important;
}
</style>