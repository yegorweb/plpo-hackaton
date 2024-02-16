<script setup>
import { onMounted } from "vue";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger);
  let foo = gsap.timeline();
  ScrollTrigger.create({
    animation: foo,
    trigger: ".plpo",
    scrub: true,
    // markers: true,
    start: "start center",
    end: "center center",
  });

  foo.to('.footer', {
            duration: 10,
            opacity:1
        })
});
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
.footer{
    z-index: -1;
    position:fixed;
    opacity: 0;
    bottom: 0;
    right: 0;
    height: 20vh;
    width: 100%;
    background-color: lightgreen;
}
</style>
