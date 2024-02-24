<script setup>
import { ref } from 'vue'
import axios from 'axios'
import { useRender } from 'vue-email'
import RegTemplate from '../components/email-templates/RegTemplate.vue';

const $api = axios.create({
    withCredentials: true,
    // baseURL: 'http://localhost:3031'
    baseURL: 'https://api.plpo.ru'
})

let name = ref('')
let phone = ref('')
let snackbar = ref(false)
let snackbarText = ref("Мы позвоним 15-20 марта для уточнения деталей")

async function reg() {
    if (name.value != '' && phone.value != '') {
        const emailHtml = await useRender(RegTemplate, { props: { name: name.value, phone: phone.value } });
        name.value = ''
        phone.value = ''
        $api.post(`/api/reg-nodemailer`, { emailHtml }).then((data => {
            data.status == 200 ? snackbarText.value = 'мы перезвоним 15-20 марта' : 'проблема с регистрацией'
            snackbar.value = true
        }))


    }
    else {
        snackbarText.value = 'введите телефон и имя'
        snackbar.value = true
    }

};
</script>
<template>
    <div>
        <v-row class="d-flex justify-center reg" id="reg">
            <v-col cols='12' md="4" class="ma-8 pa-8">
                <h1 class="text-center title">Регистрация</h1>
                <v-form>
                    <v-text-field name="name" v-model="name" label="Фамилия Имя"></v-text-field>
                    <v-text-field name="phone" v-model="phone" label="Телефон"></v-text-field>
                    <div class="d-flex justify-center">
                        <v-btn @click='reg()' color="#F90007" text-color="black">отправить</v-btn>
                    </div>

                </v-form>
            </v-col>

        </v-row>
        <v-snackbar v-model="snackbar" multi-line timeout='5000' color="#F90007">
            {{ snackbarText }}

            <template v-slot:actions>
                <v-btn color="#EAEAC3" variant="outlined" @click="snackbar = false">
                    Закрыть
                </v-btn>
            </template>
        </v-snackbar>
    </div>
</template>
<style scoped>
.reg {
    background: #293128;
    color: #EAEAC3;
}

.title {
    font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);

    text-transform: uppercase;
    font-weight: 600;
}
</style>