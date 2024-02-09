<script setup>
</script>
<template>
  <v-row>
    <v-col>
      <v-timeline align="start">

        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          Понедельник
        </v-timeline-item>

        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          Вторник
        </v-timeline-item>

        <v-timeline-item>
          <template v-slot:opposite> Opposite content </template>
          Среда
        </v-timeline-item>

      </v-timeline>
    </v-col>
  </v-row>
</template>
<style scoped>

</style>
