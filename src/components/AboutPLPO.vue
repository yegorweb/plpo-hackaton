<script setup>
import { onMounted, watch, ref } from "vue";
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";

onMounted(() => {
gsap.registerPlugin(ScrollTrigger);

let tl=gsap.timeline({repeat: -1,})
    tl.to(".sponsor", {
      y: -15, 
      stagger: {amount:2},
      scale:1.05,
    })
    tl.to(".sponsor", {
      y: 15, 
      stagger: {amount:2},
      scale:1.05,
    },"<45%")
    tl.to(".sponsor", { 
      y: 0, 
      stagger: {amount:1},
      scale:1,
    },"<45%")
})
</script>
<template>
    <div class="plpo">
        <h1 class="text-center title">Спонсоры</h1>
        <div style="height: 25dvh; background:#EAEAC3; overflow: scroll;" class="d-flex align-center justify-md-center">
            
            <a href="https://vk.com/bastion18" target="_blank" class="sponsor">
                <img src="../assets/bastion.jpg" alt="">
            </a>
           
            <a href="https://vk.com/zooglazov" target="_blank" class="sponsor">
                <img src="../assets/bk.png" alt="">
            </a>
            <a href="https://plpo.ru/posters" target="_blank" class="sponsor">
                <img src="../assets/plpo.png" alt="">
            </a>
            <a href="https://qbit-club.com/#/" target="_blank" class="sponsor">
                <img src="../assets/qbit.png" alt="">
            </a>
            <a href="https://gorodaivesi.ru/" target="_blank" class="sponsor">
                <img src="../assets/giv.png" alt="">
            </a>
            <a href="https://vk.com/grif_trik" target="_blank" class="sponsor">
                <img src="../assets/trik.png" alt="">
            </a>
            <a href="https://proviant.store/#/hello" target="_blank" class="sponsor">
                <img src="../assets/pro.png" alt="">
            </a>

        </div>
        <div style="height: 35dvh;">

        </div>


    </div>
</template>
<style scoped>
.plpo {

    height: 67dvh;
}

img {
    max-width: 150px;
    margin: 10px;
}

.title {
    font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
    background: #EAEAC3;
    text-transform: uppercase;
    font-weight: 600;
}
.footer_overlay{
    height: 25vh;
    position:relative;
    z-index:-4;
}
.sponsor{
    box-shadow: 1px;
}
</style>