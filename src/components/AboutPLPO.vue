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
        trigger: '.plpo',
        // endTrigger: '.footer',
        // pin: true,
        scrub: true,
        start: 'top',
        // pinSpacing: false
    })

    tl.to('.plpo', {
        backgroundColor: "#28a92b",
        duration: 5,
        scaleX: 1.2
    })
        .to('.plpo', {
            backgroundColor: "#ffffff",
            duration: 2,
            scale: 1.2
        })
        .to('.plpo', {
            backgroundColor: "#ffffff",
            duration: 2,
            scale: 1
        })
})
</script>
<template>
    <v-row justify="center">
        <v-col class="plpo" cols="10">
        
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

        </h3>
        </v-col>
    </v-row>
</template>
<style scoped>
.plpo {
    height: 1500px;
    background-color: blue;
}
</style>