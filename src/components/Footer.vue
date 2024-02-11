<script setup>
import { onMounted } from 'vue'
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";

// gsap работает только на onMounted
onMounted(() => {

    gsap.registerPlugin(ScrollTrigger);
    let foo = gsap.timeline()
    ScrollTrigger.create({
        animation: foo,
        trigger: '.plpo',
        // endTrigger: '.footer',
        scrub: true,
        markers: true,
        start: 'center 200px',
        end: '+=300px',
    })

    foo.to('.footer', {
        duration: 2,
        y:-150,
        scaleY:1
    })
    .to('.footer', {
        duration: 1,
        y:0,
        scaleY:1
    })
})
</script>
<template>
    <div class="footer">
            <h1>Футер</h1>
            <h1>Футер</h1>
            <h1>Футер</h1>
            <h1>Футер</h1>
        </div>
</template>
<style scoped>
.footer {
    height: 300px;
    background-color:olive;
}
</style>