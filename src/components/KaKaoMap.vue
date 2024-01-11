<template>
    <div class="wrapper">
        <div ref="container"></div>
    </div>
</template>
<script setup>
import { ref, onMounted } from 'vue'
onMounted(() => {
    if (window.kakao?.maps) {
        console.log(`KakaoMapComp.vue - 이미 map 있음`, window.kakao.maps)
        initMap()
    } else {
        console.log(`KakaoMapComp.vue - map script loading 필요`)
        loadScript()
    }
})

const loadScript = () => {
    const key = '0bb962b6fe8fe8a01a0a458fa5e4befb'   // env에 등록된 키 가져오기
    const script = document.createElement('script')
    // 동적 로딩을 위해서 autoload=false 추가
    script.src = `//dapi.kakao.com/v2/maps/sdk.js?autoload=false&appkey=${key}&libraries=services`
    // kakaomap script loading 후 initMap 실행
    script.addEventListener('load', () => kakao.maps.load(initMap))
    document.head.appendChild(script)
}

let map = null
const container = ref(null)

const initMap = () => {
    const options = {
        center: new kakao.maps.LatLng(37.25537043735095, 126.98375020014598),
        level: 2
    }
    map = new kakao.maps.Map(container.value, options)

    var geocoder = new kakao.maps.services.Geocoder()

    geocoder.addressSearch('경기 수원시 권선구 고색동 986번지 수원종합공구단지 302동', function(result, status) {
        // 정상적으로 검색이 완료됐으면 
        if (status === kakao.maps.services.Status.OK) {
            var coords = new kakao.maps.LatLng(result[0].y, result[0].x);
            // 결과값으로 받은 위치를 마커로 표시합니다
            var marker = new kakao.maps.Marker({
                map: map,
                position: coords
            });

            // 인포윈도우로 장소에 대한 설명을 표시합니다
            var infowindow = new kakao.maps.InfoWindow({
                content: '<div style="width:150px;text-align:center;padding:6px 0;">미래다이아몬드</div>'
            });
            infowindow.open(map, marker);

            // 지도의 중심을 결과값으로 받은 위치로 이동시킵니다
            map.setCenter(coords);
        } 
        });   
}
</script>
<style scoped lang="scss">
.wrapper {
    background: greenyellow;
    height: 100%;
    width: 100%;

    & div:first-child {
        width: 100%;
        height: 400px;
    }
}
</style>
