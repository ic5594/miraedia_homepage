<script setup>
// example components
import { ref, watch } from 'vue'
import DefaultInfoCard from "../../../../examples/cards/infoCards/DefaultInfoCard.vue";
import CenteredBlogCard from "../../../../examples/cards/blogCards/CenteredBlogCard.vue";
import BlogCarImg from "../../../../assets/img/mireadia/cominto_01.png"
import KaKaoMap from "@/components/KaKaoMap.vue"
import { useRoute } from "vue-router"

const route = useRoute()

const query = ref(route.query.type)


watch(route, () => {
    query.value = route.query.type
})
</script>
<template>
    <section class="py-7">
        <div class="container">
            <div class="row align-items-center" style="justify-content: center;">
                <template v-if="query == 'greeting'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">인사말</h1>
                    <div class="col-lg-6" >
                        <h3 class="font-weight-bolder mt-3">주요취급품목</h3>
                        <br>
                        <div class="row justify-content-start">
                            <DefaultInfoCard color="info" icon="public" title="전착 다이아몬드"/>
                            <DefaultInfoCard color="info" icon="payments" title="레진 다이아몬드"/>
                        </div>
                        <div class="row justify-content-start mt-4">
                            <DefaultInfoCard color="info" icon="apps" title="메탈 다이아몬드"/>
                            <DefaultInfoCard color="info" icon="3p" title="PCD & PCBN INSERT"/>
                        </div>
                    </div>
                </template>
                <template v-else-if="query == 'trading'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">주요거래선</h1>
                    <div class="col-lg-6" >
                        <h3 class="font-weight-bolder mt-3">
                            <img src="../../../../assets//img//mireadia/check_icon.png">미래다이아몬드 연혁</h3>
                        <br>
                        <h5 class="font-weight-bolder mt-3" style="height: auto; line-height: 3rem;">
                            1.  2000년 3월: 설립
                            <br>
                            2.  2002년 12월: 이화다이아몬드 협력업체등록
                            <br>
                            3.  2003년 4월: ㈜프라임 메데택 협력업체등록
                            <br>
                            4.  2007년 3월: ㈜디나옵틱스 협력업체등록
                            <br>
                            5.  2008년 9월: ㈜덴티움 협력업체등록
                            <br>
                            6.  2009년 2월: 사업장 이전(고색동)
                            <br>
                            7.  2010년 2월: ㈜마부치 코리아 협력업체등록
                            <br>
                            8.  2012년 4월: ㈜신흥엠에스티 협력업체등록
                        </h5>
                    </div>
                </template>
                <template v-else-if="query == 'map'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">약도</h1>
                    <div class="col-lg-6">
                        <h4 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">주소: 경기도 수원시 권선구 권선로 308-18, 302-213호</h4>
                        <KaKaoMap/>
                    </div>
                </template>
                
                <div class="col-lg-4 mt-lg-0 mt-6">
                    <CenteredBlogCard
                        :image="BlogCarImg"
                        title="이메일 보내기"
                        description="미래다이아몬드와 소통하기위해 이메일을 보내주세요!" />
                </div>
            </div>
        </div>
    </section>
</template>
