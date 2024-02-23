<script setup>
import { ref, watch, computed } from 'vue'
import Start from '../components/Start.vue';
import Timeline from '../components/Timeline.vue'
import Posters from '../components/Posters.vue'
import PrizeFund from "../components/PrizeFund.vue";
import Criteries from "../components/Criteries.vue";
import Rules from "../components/Rules.vue";
// import Sponsors from "../components/Sponsors.vue";
import FAQ from "../components/FAQ.vue";
import Footer from "../components/Footer.vue";
import ForWho from "../components/ForWho.vue";
import Reg from "../components/Reg.vue";
import AboutPLPO from "../components/AboutPLPO.vue";


import { useElementVisibility } from '@vueuse/core'
const target = ref(null)
const targetIsVisible = useElementVisibility(target)


let zindex = computed(() => {
    return targetIsVisible.value ? 'on' : 'under'
})
</script>
<template>
    <Start></Start>
    <Posters />

    <PrizeFund></PrizeFund>
    <v-row class="pa-8" style="background: #EAEAC3;">
        <v-col cols="12" md="6" class=" rules-col">
            <Rules />
        </v-col>
        <v-col cols="12" md="6" class=" criteries-col">
            <Criteries />
        </v-col>
    </v-row>
    <Timeline></Timeline>

    <!-- <Sponsors></Sponsors> -->
    <!-- <FAQ></FAQ>
    <ForWho></ForWho> -->
    <Reg></Reg>
    <div style="position: relative;:">
        <AboutPLPO></AboutPLPO>
        <div ref="target"></div>
        <Footer class="footer" :class='zindex'></Footer>
    </div>
</template>
<style scoped>
.rules-col {
    transform: rotate(-3deg);
}

.criteries-col {
    transform: rotate(1deg);
}

.footer {

    height: 200px;
    position: fixed;
    bottom: 0;
    right: 0;
    width: 100%;
    background: black;
    color: #EAEAC3;
}

.on {
    z-index: 1;
}

.under {
    z-index: -1;
}
</style>