<script setup>
import { onMounted, onUnmounted } from "vue";

//example components
import NavbarDefault from "../..//examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../examples/footers/FooterDefault.vue";
import Header from "../../examples/Header.vue";


// sections
import PresentationPages from "./Sections/PresentationPages.vue";

//swiper
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

import 'swiper/css/pagination';
import 'swiper/css/navigation';

// import './style.css';

// import required modules
import { Autoplay, Pagination, Navigation } from 'swiper/modules';
import MainBg1 from '@/assets/img/mireadia/main_bg1.gif'
import MainBg2 from '@/assets/img/mireadia/main_bg2.gif'
import MainBg3 from '@/assets/img/mireadia/main_bg3.gif'

const modules = [Autoplay, Pagination, Navigation]

const mainImg = [
    MainBg1, MainBg2, MainBg3
]

//hooks
const body = document.getElementsByTagName("body")[0];
onMounted(() => {
    body.classList.add("presentation-page")
    body.classList.add("bg-gray-200")
});
onUnmounted(() => {
    body.classList.remove("presentation-page")
    body.classList.remove("bg-gray-200")
});
</script>
<template>
    <div class="container position-sticky z-index-sticky top-0">
        <div class="row">
            <div class="col-12">
                <NavbarDefault :sticky="true" />
            </div>
        </div>
    </div>
    <Header>
        <div class="page-header min-vh-75">
            <div class="container">
                <swiper :spaceBetween="30" 
                    :centeredSlides="true" 
                    :autoplay="{
                        delay: 2500,
                        disableOnInteraction: false,
                    }" 
                    :loop="true"
                    :pagination="{
                        clickable: true,
                    }" 
                    :navigation="true" 
                    :modules="modules" 
                    class="mySwiper">
                    <template v-for="(item, index) in mainImg" :key="item">
                        <swiper-slide>
                            <img class="swiper_area" :src="item" :index="index">
                        </swiper-slide>
                    </template>
                </swiper>
                <div class="row">
                    <div class="col-lg-7 text-center mx-auto position-relative">
                        <h1 class="text-black pt-5 me-2" :style="{ display: 'inline-block ' }">
                            미래다이아몬드
                        </h1>
                        <p class="lead text-black mt-3" :style="{ fontWeight: '500' }">
                            산업용 다이아몬드공구 전문기업
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </Header>

    <div class="card card-body blur shadow-blur mx-3 mx-md-4 mt-n6">
        <PresentationPages />
    </div>
    <DefaultFooter />
</template>
<style scoped>
.container {
    width: 100% !important;
    max-width: 100% !important;
    --bs-gutter-x: 0;
}
.swiper_area{
    width: 100%; 
}
</style>
