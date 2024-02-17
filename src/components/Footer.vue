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
    start: "center center",
    end: "center+=200px center",
  });

  foo.to('.footer', {
    duration: 10,
    opacity: 1,
  })
});
</script>
<template>
  <div class="footer" justify="center">
    <div class="">
      <h1 class="text-center">Plpo.ru</h1>
      <h3 class="text-center">Калиннина, 2а</h3>
      <div class="text-center">
        тел.<a href="tel:+79068970429">89068970429</a>
      </div>
    </div>
    <div class="d-flex justify-space-between mt-8">
      <div class="">
        Сделано в Кубит
      </div>
      <div class="justify-end d-flex">
        <a href="https://vk.com/qbitclub" class="mr-8">
          <img src="../assets/Vk.png">
        </a>
        <a href="https://t.me/plporu">
          <img src="../assets/Tg.png">
        </a>
      </div>
    </div>
  </div>
</template>
<style scoped>
img {
  width: 30px;
  height: 30px;
}

a:link {
  color: black;
  text-decoration: none;
}

.footer {
  z-index: -1;
  margin: 0;
  position: fixed;
  opacity: 0;
  bottom: 0;
  right: 0;
  height: 20vh;
  width: 100%;
  background-color: wheat;
}
</style>
