<script setup>
import ExampleCard from "../components/ExampleCard.vue";
import CenteredBlogCard from "@/examples/cards/blogCards/CenteredBlogCard.vue";
import BlogCarImg from "@/assets/img/mireadia/cominto_01.png"
import { ref, onUnmounted, onMounted } from 'vue'

import Typed from "typed.js";

const mainMenuList = ref([
    { name: '레진 다이아몬드', img: 'src/assets/img/mireadia/main01.jpg', route: 'about', query: { type: 'cutter' } },
    { name: '전착 다이아몬드', img: 'src/assets/img/mireadia/main02.jpg', route: 'about', query: { type: 'lotari' } },
    { name: 'PCD & PCBN', img: 'src/assets/img/mireadia/main03.jpg', route: 'about', query: { type: 'pcd' } },
    { name: '메탈 다이아몬드', img: 'src/assets/img/mireadia/main04.jpg', route: 'about', query: { type: 'metal' } }
])


const body = document.getElementsByTagName("body")[0];

onMounted(() => {
    body.classList.add("about-us");
    body.classList.add("bg-gray-200");

    console.log('screen.width', window.innerWidth)
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

const mobileCheck = ref(window.innerWidth < 1350 ? true : false)

</script>
<template>
    <section>
        <div class="container mt-5">
            <div class="row">
                <div class="pre_page_area">
                    <h2 class="text-black" style="height: 10rem; text-align: center;">
                        귀사와 함께 할 수 있기를 바랍니다.
                        <br>
                        <span class="text-black" id="typed"></span>
                    </h2>
                    <div id="typed-strings">
                        <h3>품질 단가 납기에 최선을 다하는 기업
                            <br>미래 다이아몬드
                        </h3>
                    </div>
                    <p class="lead text-black opacity-7" style="text-align: center; margin-top: 4rem;">
                        미래다이아몬드 홈페이지 방문을 진심으로 환영합니다.<br>
                        저희는 산업용 다이아몬드 공구분야에서 다양한 경험과 노하우를
                        갖춘 최고의 전문기업입니다.
                    </p>
                </div>

                <div class="main_card_area">
                    <div class="main_card_list" :class="{ mobile: mobileCheck }">
                        <ExampleCard v-for="(item) in mainMenuList" class="shadow-lg" :key="item" style="margin: 3% !important;"
                            :title="item.name" :image="item.img" :route="item.route" :query="item.query" />
                    </div>

                    <div class="col-lg-4 mt-lg-0 mt-5">
                        <CenteredBlogCard :image="BlogCarImg" title="이메일 보내기" description="미래다이아몬드와 소통하기위해 이메일을 보내주세요!" />
                    </div>
                </div>


            </div>
        </div>
    </section>
</template>
<style scoped>
.pre_page_area {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.main_card_area {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
}
.main_card_area .mobile {
    justify-content: space-evenly;
    flex-direction: column;
    align-content: center;
    align-items: center;
}

.main_card_list {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}
</style>
