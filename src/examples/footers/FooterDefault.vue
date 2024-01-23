<script setup>
import logoDark from "@/assets/img/mireadia/new_logo_01.png";
defineProps({
    brand: {
        type: Object,
        name: String,
        logo: String,
        route: "",
        default: () => ({
            name: "MiraeDiamond",
            logo: logoDark,
            route: "/"
        })
    },
    socials: {
        type: Array,
        icon: String,
        link: String,
        default: () => [
            {
                icon: '<i class="fab fa-facebook text-lg opacity-8"></i>',
                link: "https://www.facebook.com/CreativeTim/"
            },
            {
                icon: '<i class="fab fa-twitter text-lg opacity-8"></i>',
                link: "https://twitter.com/creativetim"
            },
            {
                icon: '<i class="fab fa-dribbble text-lg opacity-8"></i>',
                link: "https://dribbble.com/creativetim"
            },
            {
                icon: '<i class="fab fa-github text-lg opacity-8"></i>',
                link: "https://github.com/creativetimofficial"
            },
            {
                icon: '<i class="fab fa-youtube text-lg opacity-8"></i>',
                link: "https://www.youtube.com/channel/UCVyTG4sCw-rOvB9oHkzZD1w"
            }
        ]
    },
    menus: {
        type: Array,
        name: String,
        items: {
            type: Array,
            name: String,
            href: String
        },
        default: () => [
           
        ]
    }
});
</script>
<template>
    <footer class="footer pt-5 mt-5">
        <div class="container">
            <div class="row">
                <div class="foot_area">
                    <img :src="brand.logo" style="width: 12rem;" alt="main_logo" />
                    <br>
                </div>
                <div class="col-12">
                    <div class="text-center">
                        <p class="text-dark my-4 font-weight-normal">
                            Copyright © 2000-2024 MIRAE DIAMOND Allright Reserved
                            {{ new Date().getFullYear() }}
                            302-213, 986, Gosaek-dong, Gweonsun-gu, Suwon-si, Kyunggi-do, Korea
                            <br>
                            Tel: +82-31-254-4670
                            Fax: +82-31-363-3976
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>
<style scoped>
.foot_area {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    align-items: center;
}
</style>
