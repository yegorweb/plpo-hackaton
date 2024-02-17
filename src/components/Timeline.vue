<script setup>
</script>
<template>
  <div class="d-flex align-center flex-column pa-8 timeline">
    <h1 class="text-center">Расписание</h1>
    <v-divider :thickness="10" color="#F90007"  class="border-opacity-100 w-100"></v-divider>
    <v-timeline side="end" align="start">
    <v-timeline-item
      dot-color="#F90007"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">11.00</strong>
        <div>
          <strong>Регистрация</strong>
          <!-- <div class="text-caption">
            Mobile App
          </div> -->
        </div>
      </div>
    </v-timeline-item>

    <v-timeline-item
      dot-color="#676947"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">11.30</strong>
        <div>
          <strong>Старт хакатона</strong>
         
        </div>
      </div>
    </v-timeline-item>

    <v-timeline-item
      dot-color="#F90007"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">12.30</strong>
        <div>
          <strong>Точка контроля</strong>
        </div>
      </div>
    </v-timeline-item>

    <v-timeline-item
      dot-color="#676947"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">14.30</strong>
        <div>
          <strong>Завершение разработки</strong>
        </div>
      </div>
    </v-timeline-item>
    <v-timeline-item
      dot-color="#F90007"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">14.45</strong>
        <div>
          <strong>Презентация</strong>
        </div>
      </div>
    </v-timeline-item>
    <v-timeline-item
      dot-color="#676947"
      size="small"
    >
      <div class="d-flex">
        <strong class="me-4">15.15</strong>
        <div>
          <strong>Объявление победителей</strong>
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
  </div>


</template>
<style scoped>
.timeline{
  z-index: 3;
}
</style>
