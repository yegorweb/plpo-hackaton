<script setup>
import { ref, watch, computed } from 'vue'
import vk from '../assets/vk.svg'
import telegram from '../assets/telegram.svg'

let hi = () => {
  alert('hi')
}
</script>
<template>
  <div>

    <div>
      <a target="_blank" href="http://plpo.ru">
        <h1 class="text-center site-url">plpo.ru</h1>
      </a>
      <a target="_blank"
        href="https://yandex.ru/maps/org/klub_programmirovaniya_kubit/127822682088/?ll=52.689578%2C58.140302&z=16.82">
        <h3 class="text-center">Калиннина, 2а</h3>
      </a>
      <div class="text-center">
        тел.<a href="tel:+79068970429">89068970429</a>
      </div>
      <div class="text-center">
        <a href="https://t.me/plporu" target="_blank">
          <img class="ma-2" :src="telegram" alt=""></a>

        <a href="https://vk.com/plporu" target="_blank"><img class="ma-2" :src="vk" alt=""></a>

      </div>
      <div class="text-center">
        <a target="_blank" href="http://qbit-club.com">
          © Сделано в Кубит, 2024 </a>
      </div>
      <!-- 
      <div>Адрес: <a target="_blank"
          href="https://yandex.ru/maps/org/klub_programmirovaniya_kubit/127822682088/?ll=52.689578%2C58.140302&z=16.82">
          Глазов, Калинина, 2а</a> </div>
      <div>E-mail: <a href="mailto:adm-plpo@ya.ru">adm-plpo@ya.ru</a></div>
      <div class="d-flex align-center">Телеграм: <a href="https://t.me/grachevrv" target="_blank">
          https://t.me/grachevrv </a></div>

      <div class="text-center">
        <a href="https://t.me/plporu" target="_blank">
          <img class="ma-2" :src="telegram" alt=""></a>

        <a href="https://vk.com/plporu" target="_blank"><img class="ma-2" :src="vk" alt=""></a>

      </div>
      <div class="text-center">
        <a href="https://qbit-club.com" target="_blank">Сделано в Кубит</a>
      </div>
      <div class="text-center">
        © Клуб Кубит, 2023
      </div> -->
    </div>
  </div>
</template>
<style scoped>
.site-url {

  font-size: 80px;
  font-weight: bold;
  text-transform: uppercase;
  color: #F90007;
}

a:link,
a:link,
a:visited,
a:hover,
a:active {
  color: #EAEAC3;
  text-decoration: none;
}
</style>
