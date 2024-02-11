<script setup>
import Start from '../components/Start.vue';
import Timeline from '../components/Timeline.vue'
import Posters from '../components/Posters.vue'
import PriceFund from "../components/PriceFund.vue";
import Criteries from "../components/Criteries.vue";
import Rules from "../components/Rules.vue";
import Contacts from "../components/Contacts.vue";
import FAQ from "../components/FAQ.vue";
import Footer from "../components/Footer.vue";
import ForWho from "../components/ForWho.vue";
import Reg from "../components/Reg.vue";
import AboutPLPO from "../components/AboutPLPO.vue";
import { ref, onMounted, watch, computed } from 'vue'
import { useScroll } from '@vueuse/core'
const el = ref < HTMLElement | null > (null)
const { x, y } = useScroll(document.body)

const displayX = computed({
    get() {
        return x.value.toFixed(1)
    },
    set(val) {
        x.value = Number.parseFloat(val)
    },
})
const displayY = computed({
    get() {
        return y.value.toFixed(1)
    },
    set(val) {
        y.value = Number.parseFloat(val)
    },
})
console.log(displayX, displayY)
// let handleScroll = async () => {
//   let triggerHeight = body.scrollTop + body.offsetHeight + 5
// console.log(triggerHeight)
//   if (triggerHeight >= 200) {
//     console.log('sus')
//   }
//   if (triggerHeight >= body.scrollHeight) {
//     triggerHeight = body.scrollHeight
//   }
//   if (triggerHeight == document.body.scrollHeight) {
//     await posterStore.fetchPosters(posterStore.filter)
//   }
// }
// onMounted(async () => {
//     window.addEventListener('scroll', function () {
//   const scrollPosition = window.scrollY;
//   console.log(scrollPosition);
// });
// })
</script>
<template ref="el" class="wrapper" style="overflow-x: hidden;">
    <Start></Start>
    <Timeline></Timeline>
    <PriceFund></PriceFund>
    <v-row class="pa-8">
        <v-col cols="12" md="6" class="pa-0 ma-0 rules-col">
            <Rules />
        </v-col>
        <v-col cols="12" md="6" class="pa-0 ma-0 criteries-col">
            <Criteries />
        </v-col>
    </v-row>


    <Contacts></Contacts>
    <FAQ></FAQ>
    <ForWho></ForWho>
    <AboutPLPO></AboutPLPO>
    <Reg></Reg>
    <Footer></Footer>
</template>
<style scoped>
body {
    height: 90dvh;
    overflow: auto;

    &::-webkit-scrollbar {
        display: none;
    }
}
.rules-col{
    transform: rotate(-3deg);
}
.criteries-col{
    transform: rotate(1deg); 
}
</style>