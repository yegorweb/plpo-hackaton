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
    markers: true,
    scrub: true,
    start: "start+=200px center",
    end: "center+=500px center",
  });

  foo.to('.footer', {
            duration: 10,
            top:-300,
        })
        .to('.footer', {
            duration: 10,
            top:0
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
.footer {
    z-index: -1;
    position: relative;
    top: -300px;
    left: 0;
    right: 0;
    bottom: 0;
  height: 300px;
  width: 100%;
  background-color: olive;
}
</style>
