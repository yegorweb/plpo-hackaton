<script setup>
import Start from '../components/Start.vue';
import Timeline from '../components/Timeline.vue'
import Posters from '../components/Posters.vue'
import PrizeFund from "../components/PrizeFund.vue";
import Criteries from "../components/Criteries.vue";
import Rules from "../components/Rules.vue";
import Contacts from "../components/Contacts.vue";
import FAQ from "../components/FAQ.vue";
import Footer from "../components/Footer.vue";
import ForWho from "../components/ForWho.vue";
import Reg from "../components/Reg.vue";
import AboutPLPO from "../components/AboutPLPO.vue";
</script>
<template>
    <Start></Start>
    <Posters/>
    <Timeline></Timeline>
    <PrizeFund></PrizeFund>
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
    <Reg></Reg>
    <AboutPLPO></AboutPLPO>
    <Footer class="position_footer"></Footer>
</template>
<style scoped>
/* .position_footer{
    z-index: -1;
    position: relative;
    top: 0;
    left: 0;
    right: 0;
    bottom: 100px;
} */
.rules-col{
    transform: rotate(-3deg);
}
.criteries-col{
    transform: rotate(1deg); 
}
</style>