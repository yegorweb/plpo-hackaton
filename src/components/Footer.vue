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
    end: "center+=100px center",
  });

  foo.to(".footer", {
    duration: 10,
    opacity: 1,
  });

  let bounce = gsap.timeline()
  ScrollTrigger.create({
    animation: bounce,
    trigger: ".plpo",
    markers: true,
    start: "center+=100px center",
    end: "+=100px bottom",

  });
  bounce.to(".main_text", {
    duration: 0.5,
    scale:1.1
  }).to(".main_text", {
    duration: 0.5,
    scale:1
  });

});
</script>
<template>
  <div class="footer">

    <div class="">
      <h1 class="text-center main_text">Plpo.ru</h1>
      <h3 class="text-center divider pb-4">Калиннина, 2а</h3>
    </div>
      <div class="text-center mt-4">тел.<a href="tel:+79068970429">89068970429</a></div>

    <div class="d-flex justify-space-around">

      <div class="ml-8 footer_second_col">Сделано в Кубит</div>

      <div class="justify-end d-flex footer_second_col mr-8">
        <a href="https://vk.com/qbitclub" class="mr-8">
          <img src="../assets/Vk.png" />
        </a>
        <a href="https://t.me/plporu">
          <img src="../assets/Tg.png" />
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
  background-color: #ececc1;
  z-index: -1;
  margin: 0;
  position: fixed;
  opacity: 0;
  bottom: 0;
  right: 0%;
  left: 10%;
  height: 25vh;
  width: 80%;
}
.footer_second_col{
  box-sizing: content-box;
  width: 50%;
}
.divider{
  border-bottom: 5px solid #000;
}
</style>
