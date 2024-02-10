<script setup>
import { onMounted } from "vue";
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";


// gsap работает только на onMounted
onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);
    let tl = gsap.timeline()
    tl.to('.poster', {
        rotation: 360
    })

    ScrollTrigger.create({
        animation: tl,
        trigger: '.poster-container',
        start: '-=25%',
        end: '+=25%',
        scrub: 1,
        pin: true,
        anticipatePin: 1,
    })

})
</script>
<template>
    <div class="poster-container">
        <div class="row">
            <div class="poster one"></div>
            <div class="poster two"></div>
        </div>
        <div class="row">
            <div class="poster three"></div>
            <div class="poster four"></div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.poster {
    aspect-ratio: calc(210 / 297);
    height: 200px;
    background-color: blue;
    margin: 5px;
}

.poster-container {
    display: flex;
    flex-direction: column;
    height: 100vh;

    .row {
        width: 100%;
        display: flex;
        justify-content: center;
    }
}
</style>