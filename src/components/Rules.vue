<script setup>
import { onMounted, watch, ref } from "vue";
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)
  gsap.from(".rules", {
    scrollTrigger: {
      trigger: ".rules",
      start:'top center',
    },
    x: -50,
  });

})

</script>
<template>
    <div class="rules" id="rules">
        <h1 class="text-center">Правила</h1>
      <p>Делаем афишу на месте</p>
      <p>Афиша реального события или места</p>
      <p>Можно взять логотипы и фото</p>
      <p>Нельзя готовую графику и рисунки</p>
      <p>Работаем 3 часа</p>
      <p>От 16 лет</p>
        
 
        
    </div>
</template>
<style scoped>
.rules {

  /* height: 300px; */
  color: #EAEAC3;
  background: #000;
  font-size: clamp(0.75rem, 0.4821rem + 0.8571vw, 1.125rem);
  text-transform: uppercase;
  font-weight: 600;
  padding: 5% 10% 10% 10%;


}

h1 {
  font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
  color: #EAEAC3;
  text-transform: uppercase;
  font-weight: 600;
}
</style>