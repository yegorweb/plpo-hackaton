<script setup>
import { onMounted } from 'vue'
import { gsap } from "gsap"
import { ScrollTrigger } from "gsap/ScrollTrigger";

// gsap работает только на onMounted
onMounted(() => {

    gsap.registerPlugin(ScrollTrigger);
    let tl = gsap.timeline()
    ScrollTrigger.create({
        animation: tl,
        trigger: '.sus',
        // endTrigger: '.footer',
        // pin: true,
        scrub: true,
        start: 'top 200px',
        end: '+=1300px',
        // pinSpacing: false
    })

    tl.to('.sus', {
        backgroundColor: "#28a92b",
        ease: "none",
        duration: 5,
        scale: 1.2
    })
        .to('.sus', {
            backgroundColor: "#ffffff",
            duration: 2,
        })
        .to('.sus', {
            backgroundColor: "#ffffff",
            ease: "none",
            duration: 2,
            scale: 0.95
        })
})
</script>
<template>
    <v-row class="d-flex justify-center">
        <v-col cols='4'>
            <h1>Регистрация</h1>
            <v-form class="mt-2">
                <v-text-field name="name" label="Имя Фамилия"></v-text-field>
                <v-text-field name="phone" label="номер телефона"></v-text-field>
                <v-btn type="submit" class="btn btn-lg btn-dark btn-block">отправить</v-btn>
            </v-form>

            Зарегистрируйся сейчас, иначе
            <h3>
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
                sdghasuidgasuidgsuidgasasydgyasdgyausdguaysysysysysysysysysysysysysysgfy8egq8fbg9quefbhqueifueb8yfg2v8
                r24gr2 y84rgv2y8 r82 46rt2468rtx27 r823 r823t8tx2rt823 r8 23rt87
            </h3>
        </v-col>
    </v-row>
</template>
<style scoped>
.sus {
    height: 1500px;
    background-color: blue;
}</style>