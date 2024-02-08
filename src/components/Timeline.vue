<script setup>
import PriceFund from "../components/PriceFund.vue";
import Criteries from "../components/Criteries.vue";
import Rules from "../components/Rules.vue";
</script>
<template>
  <v-row>
    <v-col>
      <v-timeline align="start">
        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          <PriceFund></PriceFund>
        </v-timeline-item>
        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          <Criteries></Criteries
        ></v-timeline-item>
        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          <Rules></Rules
        ></v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>
<style scoped></style>
