<script setup>
import { onMounted, onUnmounted, watch, ref } from "vue";

//example components
import DefaultNavbar from "../../../examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../../examples/footers/FooterDefault.vue";

//image
import bg1 from "@/assets/img/mireadia/diamond_bg_01.png";
import bg2 from "@/assets/img/mireadia/diamond_bg_02.png";
import bg3 from "@/assets/img/mireadia/diamond_bg_03.png";
import bg4 from "@/assets/img/mireadia/diamond_bg_04.png";
import bg5 from "@/assets/img/mireadia/diamond_bg_05.png";
import bg6 from "@/assets/img/mireadia/diamond_bg_06.png";

import { useRoute } from "vue-router"

const route = useRoute()

const query = ref(route.query.type)

//dep
import Typed from "typed.js";

//sections
import Information from "./Sections/AboutInformation.vue";
// import AboutTeam from "./Sections/AboutTeam.vue";
// import Featuring from "./Sections/AboutFeaturing.vue";
// import Newsletter from "./Sections/AboutNewsletter.vue";

const body = document.getElementsByTagName("body")[0];
//hooks
onMounted(() => {
    body.classList.add("about-us");
    body.classList.add("bg-gray-200");

    if (document.getElementById("typed")) {
        // eslint-disable-next-line no-unused-vars
        var typed = new Typed("#typed", {
            stringsElement: "#typed-strings",
            typeSpeed: 90,
            backSpeed: 90,
            backDelay: 200,
            startDelay: 500,
            loop: true,
        });
    }
});

onUnmounted(() => {
    body.classList.remove("about-us");
    body.classList.remove("bg-gray-200");
});

const bg = ref(bg1)

watch(route, () => {
    query.value = route.query.type
    if (query.value == 'greeting' || query.value == 'trading' || query.value == 'map') {
        bg.value = bg1
    } else if (query.value == 'surgery' || query.value == 'cutter') {
        bg.value = bg2
    } else if (query.value == 'metal' || query.value == 'cora') {
        bg.value = bg3
    } else if (query.value == 'lotari' || query.value == 'id' || query.value == 'disk' || query.value == 'electrode') {
        bg.value = bg4
    } else if (query.value == 'pcd' || query.value == 'insert') {
        bg.value = bg5
    } else {
        bg.value = bg6
    }
})
</script>
<template>
    <DefaultNavbar :action="{
        route: 'javascript:;',
        label: 'Buy Now',
        color: 'btn-white',
    }" transparent />
    <header class="bg-gradient-dark">
        <div class="page-header min-vh-35" :style="{ backgroundImage: `url(${bg})` }">
            <span class="mask bg-gradient-dark opacity-6"></span>
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-lg-8 text-center mx-auto my-auto">
                        <template v-if="query == 'greeting' || query == 'trading' || query == 'map'">
                            <h1 class="text-white">
                                회사소개
                            </h1>
                        </template>
                        <template v-else-if="query == 'surgery' || query == 'cutter'">
                            <h1 class="text-white">
                                레진 다이아몬드
                            </h1>
                        </template>
                        <template v-else-if="query == 'metal' || query == 'cora'">
                            <h1 class="text-white">
                                메탈 다이아몬드
                            </h1>
                        </template>
                        <template v-else-if="query == 'lotari' || query == 'id' || query == 'disk' || query == 'electrode'">
                            <h1 class="text-white">
                                전착 다이아몬드
                            </h1>
                        </template>
                        <template v-else-if="query == 'pcd' || query == 'insert'">
                            <h1 class="text-white">
                                INSERT
                            </h1>
                        </template>
                        <template v-else>
                            <h1 class="text-white">
                                TOOLING
                            </h1>
                        </template>
                        <!-- <h1 class="text-white">
                            귀사와 함께 할 수 있기를 바랍니다.
                            <br>
                            <span class="text-white" id="typed"></span>
                        </h1>
                        <div id="typed-strings">
                            <h1>품질</h1>
                            <h1>단가</h1>
                            <h1>납기</h1>
                            <h1>품질 단가 납기에 최선을 다하는 기업
                                <br><a style="color: darkgray">미래 다이아몬드</a>
                            </h1>
                        </div>
                        <p class="lead mb-4 text-white opacity-8">
                            미래다이아몬드 홈페이지 방문을 진심으로 환영합니다.
                            저희는 산업용 다이아몬드 공구분야에서 다양한 경험과 노하우를
                            갖춘 최고의 전문기업입니다.
                        </p> -->
                    </div>
                </div>
            </div>
        </div>
    </header>
    <div class="card card-body shadow-xl mx-3 mx-md-4 mt-n6">
        <Information />
        <!-- <AboutTeam />
        <Featuring />
        <Newsletter /> -->
    </div>
    <DefaultFooter />
</template>
