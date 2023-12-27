<script setup>
import { onMounted, onUnmounted } from "vue";

//example components
import DefaultNavbar from "../../../examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../../examples/footers/FooterDefault.vue";

//image
import bg0 from "@/assets/img/mireadia/diamond_bg.png";

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

</script>
<template>
    <DefaultNavbar :action="{
        route: 'javascript:;',
        label: 'Buy Now',
        color: 'btn-white',
    }" transparent />
    <header class="bg-gradient-dark">
        <div class="page-header min-vh-75" :style="{ backgroundImage: `url(${bg0})` }">
            <span class="mask bg-gradient-dark opacity-6"></span>
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-lg-8 text-center mx-auto my-auto">
                        <h1 class="text-white">
                            귀사와 함께 할 수 있기를 바랍니다. 
                            <!-- <span class="text-white" id="typed"></span> -->
                        </h1>
                        <!-- <div id="typed-strings">
                            <h1>team</h1>
                            <h1>design</h1>
                            <h1>tool</h1>
                        </div> -->
                        <p class="lead mb-4 text-white opacity-8">
                            미래다이아몬드 홈페이지 방문을 진심으로 환영합니다.
                            저희는 산업용 다이아몬드 공구분야에서 다양한 경험과 노하우를 
                            갖춘 최고의 전문기업입니다.
                        </p>
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
