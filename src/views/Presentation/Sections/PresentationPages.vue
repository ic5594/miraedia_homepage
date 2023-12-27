<script setup>
import ExampleCard from "../components/ExampleCard.vue";
import { ref } from 'vue'

const mainMenuList1 = ref([
    { name: '레진 다이아몬드', img: 'src/assets/img/mireadia/main01.jpg', route: 'about' },
    { name: '전착 다이아몬드', img: 'src/assets/img/mireadia/main02.jpg', route: 'about' },
])

const mainMenuList2 = ref([
    { name: 'PCD & PCBN', img: 'src/assets/img/mireadia/main03.jpg', route: 'author' },
    { name: '치아교정 브라켓', img: 'src/assets/img/mireadia/main04.jpg', route: 'about' }
])

</script>
<template>
    <section class="py-5">
        <div class="container mt-5">
            <div class="row">
                <div class="col-md-8">
                    <div class="row mt-4">
                        <div class="col-md-6 mt-md-0 mt-5">
                            <ExampleCard v-for="(item) in mainMenuList1" class="shadow-lg" :key="item" :title="item.name"
                                :image="item.img" :route="item.route" />
                        </div>
                        <div class="col-md-6 mt-md-0 mt-5">
                            <ExampleCard v-for="(item) in mainMenuList2" class="shadow-lg" :key="item" :title="item.name"
                                :image="item.img" :route="item.route" />
                        </div>
                    </div>
                </div>
                <div class="col-md-3 mx-auto mt-md-0 mt-3">
                    <div class="position-sticky" style="top: 100px !important">
                        <h3>
                            Presentation Pages for Company, Landing Pages, Blogs and Support
                        </h3>
                        <h6 class="text-secondary font-weight-normal">
                            These is just a small selection of the multiple possibitilies you
                            have. Focus on the business, not on the design.
                        </h6>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
