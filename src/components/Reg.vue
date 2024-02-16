<script setup>
import { ref } from 'vue'
import axios from 'axios'
import { useRender } from 'vue-email'
import RegTemplate from '../components/email-templates/RegTemplate.vue';

const $api = axios.create({
    withCredentials: true,
    baseURL: 'http://localhost:3031'
})

let name = ref()
let phone = ref()

async function reg() {
    const emailHtml = await useRender(RegTemplate, { props: { name, phone }}); 
    name.value = ''
    phone.value = ''
    return $api.post(`/api/reg-nodemailer`,{emailHtml})
};



// gsap работает только на onMounted
// onMounted(() => {

//     gsap.registerPlugin(ScrollTrigger);
//     let tl = gsap.timeline()
//     ScrollTrigger.create({
//         animation: tl,
//         trigger: '.sus',
//         // endTrigger: '.footer',
//         // pin: true,
//         scrub: true,
//         start: 'top 200px',
//         end: '+=1300px',
//         // pinSpacing: false
//     })

//     tl.to('.sus', {
//         backgroundColor: "#28a92b",
//         ease: "none",
//         duration: 5,
//         scale: 1.2
//     })
//         .to('.sus', {
//             backgroundColor: "#ffffff",
//             duration: 2,
//         })
//         .to('.sus', {
//             backgroundColor: "#ffffff",
//             ease: "none",
//             duration: 2,
//             scale: 0.95
//         })
// })
</script>
<template>
    <v-row class="d-flex justify-center">
        <v-col class="my-8" cols="10" sm="6" md="4">
            <h1>Регистрация</h1>
            <v-form class="mt-3">
                <v-text-field v-model="name" label="Имя Фамилия"></v-text-field>
                <v-text-field v-model="phone" label="номер телефона"></v-text-field>
                <v-btn variant="outlined" @click="reg()">отправить</v-btn>
            </v-form>
        </v-col>
    </v-row>
</template>
<style scoped>
</style>