<script setup>
// example components
import { ref, watch } from 'vue'
import DefaultInfoCard from "../../../../examples/cards/infoCards/DefaultInfoCard.vue";


import KaKaoMap from "@/components/KaKaoMap.vue"
import { useRoute } from "vue-router"

const route = useRoute()

const query = ref(route.query.type)


watch(route, () => {
    query.value = route.query.type
})
</script>
<template>
    <section class="py-5">
        <div class="container">
            <div class="row align-items-center" style="justify-content: center;">
                <template v-if="query == 'greeting'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">취급품목</h1>
                    <div style="text-align: center; text-overflow: ellipsis;">
                        <br>
                        <div class="row justify-content-start">
                            <DefaultInfoCard color="info" icon="Electro Plated Tool" title="전착 다이아몬드" />
                            <DefaultInfoCard color="info" icon="Resin Bond Diamond Wheel" title="레진 다이아몬드" />
                        </div>
                        <div class="row justify-content-start mt-4">
                            <DefaultInfoCard color="info" icon="Metal Bond Diamond Wheel" title="메탈 다이아몬드" />
                            <DefaultInfoCard color="info" icon="Compax Bite" title="PCD & PCBN INSERT" />
                        </div>
                    </div>
                </template>
                <template v-else-if="query == 'trading'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">주요거래선</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img
                                src="../../../../assets//img//mireadia/check_icon.png">미래다이아몬드 연혁</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3" style="height: auto; line-height: 3rem;">
                            1. 2000년 3월: 설립
                            <br>
                            2. 2002년 12월: 이화다이아몬드 협력업체등록
                            <br>
                            3. 2003년 4월: ㈜프라임 메데택 협력업체등록
                            <br>
                            4. 2007년 3월: ㈜디나옵틱스 협력업체등록
                            <br>
                            5. 2008년 9월: ㈜덴티움 협력업체등록
                            <br>
                            6. 2009년 2월: 사업장 이전(고색동)
                            <br>
                            7. 2010년 2월: ㈜마부치 코리아 협력업체등록
                            <br>
                            8. 2012년 4월: ㈜신흥엠에스티 협력업체등록
                        </h4>
                    </div>
                </template>
                <template v-else-if="query == 'map'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">약도</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">주소:
                            경기도 수원시 권선구 권선로 308-18, 302-213호</h3>
                        <KaKaoMap />
                    </div>
                </template>
                <template v-else-if="query == 'surgery'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">성형 휠</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">레진본드
                            휠</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3">제품 설명</h4>
                        <h5 class="font-weight-bolder mt-3">레진본드는 페놀수지와 같은 열 경화성 수지를 결합재로 하여 제조됩니다.
                            <br>
                            특징으로는 우수한 연삭성과 표면조도, 치핑(cheapping)등의 가공정도가 양호하기 때문에
                            세라믹, 유리 실리콘 등 경취성 재료 및 고속도강, 철계 소결합금강등에 적용됩니다.
                        </h5>

                        <h4 class="font-weight-bolder mt-3">제품 특징</h4>
                        <h5 class="font-weight-bolder mt-3">1. 쾌삭성이 우수합니다.
                            <br>
                            2. 습식과 건식에 모두 사용됩니다.
                            <br>
                            3. 적용범위가 넓습니다.
                        </h5>

                        <h4 class="font-weight-bolder mt-3">제품 용도</h4>
                        <h5 class="font-weight-bolder mt-3">1. Diamond Wheel</h5>
                        <h5 class="font-weight-bolder mt-3">초경합금, 서멧, 세라픽의 정밀연삭에 사용됩니다.
                            <br>
                            또한, 레진본드의 탄력성이 우수하여 고조도를요하는 실리콘, 유리, 세라믹 전자부품등에 적용됩니다.
                        </h5>
                        <h5 class="font-weight-bolder mt-3">2. CBN Wheel</h5>
                        <h5 class="font-weight-bolder mt-3">주철, 고속도감, 철계 소결금속의 연삭에 사용됩니다.</h5>

                        <h4 class="font-weight-bolder mt-3">규격</h4>
                        <h5 class="font-weight-bolder mt-3">ISO규격인 휠 형상에따라 외경 및 내경의 규격, 피삭재의 종류 및 사용조건을 정확히 알아야합니다.</h5>

                        <h4 class="font-weight-bolder mt-3">집중도</h4>
                        <h5 class="font-weight-bolder mt-3">다이아몬드 휠에 사용된 다이아몬드의 체적을 나타내며, 휠의 절삭성 및 수명에 영향을 미칩니다.</h5>
                    </div>
                </template>
                <template v-else-if="query == 'cutter'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">휠 커터</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img
                                src="../../../../assets//img//mireadia/check_icon.png">레진다이아몬드 커터</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3">제품 특징</h4>
                        <h5 class="font-weight-bolder mt-3">1. 쾌삭성이 우수합니다.
                            <br>
                            2. 습식과 건식에 모두 사용됩니다.
                            <br>
                            3. 적용범위가 넓습니다.
                        </h5>

                        <h4 class="font-weight-bolder mt-3">제품 용도</h4>
                        <h5 class="font-weight-bolder mt-3">1. Diamond Wheel</h5>
                        <h5 class="font-weight-bolder mt-3">초경합금, 서멧, 세라픽의 정밀연삭에 사용됩니다.
                            <br>
                            h5  또한, 레진본드의 탄력성이 우수하여 고조도를요하는 실리콘, 유리, 세라믹 전자부품등에 적용됩니다.
                        </h5>
                        <h5 class="font-weight-bolder mt-3">2. CBN Wheel</h5>
                        <h5 class="font-weight-bolder mt-3">주철, 고속도감, 철계 소결금속의 연삭에 사용됩니다.</h5>

                        <h4 class="font-weight-bolder mt-3">규격</h4>
                        <h5 class="font-weight-bolder mt-3">ISO규격인 휠 형상에따라 외경 및 내경의 규격, 피삭재의 종류 및 사용조건을 정확히 알아야합니다.</h5>

                        <h4 class="font-weight-bolder mt-3">집중도</h4>
                        <h5 class="font-weight-bolder mt-3">다이아몬드 휠에 사용된 다이아몬드의 체적입니다.
                            <br>
                            휠의 절삭성 및 수명에 영향을 미칩니다.
                        </h5>
                    </div>
                </template>
                <template v-else-if="query == 'metal'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">메탈 휠</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img
                                src="../../../../assets//img//mireadia/check_icon.png">Metal Cup Wheel</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3">특징</h4>
                        <h5 class="font-weight-bolder mt-3">동, 주석, 코발트등의 금속분말을 결합체로 사용한 제품입니다.
                            <br>다른 결합체와 비교하여 다이아몬드 지립의 보지력이 우수합니다.
                        </h5>
                        <h5 class="font-weight-bolder mt-3">인성, 내마노성, 내열성이 매우 우수함.</h5>
                        <h5 class="font-weight-bolder mt-3">제품의 수명이 다른 결합제보다 매우 우수함.</h5>
                        <h5 class="font-weight-bolder mt-3">다른 결합제의 제품보다 높은 동력을 요함.</h5>

                        <h4 class="font-weight-bolder mt-3">용도</h4>
                        <h5 class="font-weight-bolder mt-3">산업용: 정밀가공을 요하는 산업용 소재의 에지(edge)연마
                            <br>및 초정밀 평면안마에 주로 사용됩니다.
                        </h5>
                        <h5 class="metal_img_area"><img class="metal_img"
                                src="../../../../assets//img//mireadia/metal_img_01.png">
                            <img class="metal_img" src="../../../../assets//img//mireadia/metal_img_02.png">
                        </h5>
                    </div>
                </template>

                <template v-else-if="query == 'cora'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">코아비트</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img
                                src="../../../../assets//img//mireadia/check_icon.png">Metal Core Bit</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3">특징</h4>
                        <h5 class="font-weight-bolder mt-3">동, 주석, 코발트등의 금속분말을 결합체로 사용한 제품입니다.
                            <br>다른 결합체와 비교하여 다이아몬드 지립의 보지력이 우수합니다.
                        </h5>
                        <h5 class="font-weight-bolder mt-3">인성, 내마노성, 내열성이 매우 우수함.</h5>
                        <h5 class="font-weight-bolder mt-3">제품의 수명이 다른 결합제보다 매우 우수함.</h5>
                        <h5 class="font-weight-bolder mt-3">다른 결합제의 제품보다 높은 동력을 요함.</h5>

                        <h4 class="font-weight-bolder mt-3">용도</h4>
                        <h5 class="font-weight-bolder mt-3">산업용: 정밀가공을 요하는 산업용 소재의 홀(hole)가공
                            <br>및 시료채취에 주로 사용됩니다.
                        </h5>
                        <h5 class="core_img_area"><img class="metal_img"
                                src="../../../../assets//img//mireadia/core_img_01.png">
                            <a class="font-weight-bolder mt-3">정밀 홀가공용 비트</a>
                            <br>
                            <img src="../../../../assets//img//mireadia/core_img_02.png">
                            <a class="font-weight-bolder mt-3">코아비트</a>
                            <br>
                        </h5>
                    </div>
                </template>


                <template v-else-if="query == 'lotari'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">로터리 휠</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">전착
                            휠(Electro Plated Wheel)</h3>
                        <br>
                        <h4 class="font-weight-bolder mt-3">제품 특징</h4>
                        <h5 class="font-weight-bolder mt-3">복잡한 형상의 가공에 매우 유리합니다.
                            <br>절삭성이 매우 뛰어납니다.
                            <br>단가가 비교적으로 저렴합니다.
                            <br>코딩공구이므로 수명이 짧은 것이 단점입니다.
                        </h5>

                        <h4 class="font-weight-bolder mt-3">제품 용도</h4>
                        <h5 class="font-weight-bolder mt-3">경취성이 높은 유리, 세라믹, 타일, 도자기 등의 복잡한 형상가공 및 내 외경연마에 사용.
                            <br>초경, 사파이어, 실리콘등의 난삭재 가공게 사용
                        </h5>
                    </div>
                </template>


                <template v-else-if="query == 'id'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">I.D 휠</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">I.D
                            Wheel</h3>
                        <br>

                        <h4 class="font-weight-bolder mt-3">제품 특징</h4>
                        <h5 class="font-weight-bolder mt-3">제품 및 부품의 내경 연마에 전용으로 사용되는 공구</h5>
                        <h5 class="font-weight-bolder mt-3">Diamond 및 CBN 입자가 노출되어 우수한 연삭력을 지님</h5>

                        <h4 class="font-weight-bolder mt-3">제품 용도</h4>
                        <h5 class="font-weight-bolder mt-3">초경공구의 칩포켓 가공 및 내경가공
                            <br>세라믹, 실리콘의 에지 가공등에 사용.
                        </h5>
                        <h5 class="metal_img_area"><img class="metal_img"
                                src="../../../../assets//img//mireadia/id_img_01.png">
                            <br>
                            <img class="metal_img" src="../../../../assets//img//mireadia/id_img_02.png">
                            <br>
                        </h5>
                    </div>
                </template>

                <!-- disk -->
                <template v-else-if="query == 'disk'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">DISK & POINTER</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">Disk</h3>
                        <br>
                        <img class="disk_img" src="../../../../assets//img//mireadia/disk_img_01.png">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">POINTER</h3>
                        <br>
                        <img class="disk_img" src="../../../../assets//img//mireadia/disk_img_02.png">
                    </div>
                </template>

                <!-- 전착커터 -->
                <template v-else-if="query == 'electrode'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">전착 커터(톱)</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">전착 다이아몬드 Saw</h3>
                        
                        <h5 class="font-weight-bolder mt-3">경도가 높은 취성재료의 절단 및 가공에 사용됩니다.
                            <br>세라믹, 초경 등
                        </h5>
                        <img style="width: 100%;" src="../../../../assets//img//mireadia/ele_img_01.png">
                        <br>
                        <br>
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">전착 Core Bit</h3>
                        <!-- <br> -->
                        <h5 class="font-weight-bolder mt-3">난삭재의 홀가공 및 천공에 사용됨</h5>
                        <img style="width: 90%;" src="../../../../assets//img//mireadia/ele_img_02.png">
                            
                    </div>
                </template>

                <template v-else-if="query == 'pcd'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">PCD & PCBN</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">PCD INSERT</h3>
                        <h4 class="font-weight-bolder mt-3">특징</h4>
                        <h5 class="font-weight-bolder mt-3">알루미늄 및 비철금속, 비금속의 절삭시 탁월한 표면조도 구현</h5>
                        <h5 class="font-weight-bolder mt-3">내마모성과 열전도성이 뛰어나 고속가공에서도 긴 공구 수명 보장.
                            <br>*주의: 강 및 주철절삭에는 사용이 불가능함*
                        </h5>
                        <br>
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">PCBN INSERT</h3>
                        <h4 class="font-weight-bolder mt-3">특징</h4>
                        <h5 class="font-weight-bolder mt-3">소결금속, 고경도 소재, 내열합금 등이 가공에 탁월.</h5>
                        <h5 class="font-weight-bolder mt-3">고경도 재료를 고속가공함으로써 생산성 향상 및 공정단축이 가능함.</h5>
                        <h5 class="font-weight-bolder mt-3">뛰어난 표면조도</h5>
                        

                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">ISO 규격</h3>
                        <img style="width: 100%;" src="../../../../assets//img//mireadia/pcd_img_01.png">
                    </div>
                </template>

                <!-- 초경인써트 -->
                <template v-else-if="query == 'insert'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">초경 인써트</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">PCD INSERT BASE</h3>
                        
                        <img style="width: 100%;" src="../../../../assets//img//mireadia/insert_01_img.png">
                    </div>
                </template>

                <!-- shape -->
                <template v-else-if="query == 'shape'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">휠 형상</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">휠 타입</h3>
                        
                        <img style="width: 100%;" src="../../../../assets//img//mireadia/shape_img_01.png">
                    </div>
                </template>

                 <!-- 입도환산표 -->
                 <template v-else-if="query == 'table'">
                    <h1 class="font-weight-bolder mt-2" style="text-align: center; color: #2f80ed;">입도 환산표</h1>
                    <div class="col-lg-8">
                        <h3 class="font-weight-bolder mt-3"><img src="../../../../assets//img//mireadia/check_icon.png">Mesh</h3>
                        <h5 class="font-weight-bolder mt-3">1Inch내에(가로+세로) 들어있는 눈금의 수를 나타냄.
                            <br>즉, 메쉬는 단위가 클수록 작은 눈금이 많아 촘촘하다는 의미이며 그반대 개념인 마이크론은
                            수치가 적을수록 촘촘한 것입니다.
                            <br>
                            <br>
                            마이크론은 백만분의 일이라는 분율(Parts) 개념이기 때문입니다.
                        </h5>
                        <img style="width: 100%;" src="../../../../assets//img//mireadia/mesh_img_01.png">
                    </div>
                </template>
                
            </div>
        </div>
    </section>
</template>
<style scoped>
.metal_img_area {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}

.metal_img {
    width: 15rem;
    height: 15rem;
}

.core_img_area {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
}
.disk_img {
    width: 100%;
}
</style>
