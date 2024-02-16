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



</script>
<template>
    <v-row class="d-flex justify-center">
        <v-col cols='4'>
            <h1>Регистрация</h1>
            <v-form class="mt-2">
                <v-text-field v-model="name" label="Имя Фамилия"></v-text-field>
                <v-text-field v-model="phone" label="номер телефона"></v-text-field>
                <v-btn @click="reg()" class="btn btn-lg btn-dark btn-block">отправить</v-btn>
            </v-form>
        </v-col>
    </v-row>
</template>
<style scoped></style>