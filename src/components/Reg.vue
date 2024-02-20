<script setup>
</script>
<template>
    <v-row class="d-flex justify-center reg" id="reg">
        <v-col cols='12' md="4" class="ma-8 pa-8">
            <h1 class="text-center title">Регистрация</h1>
            <v-form>
                <v-text-field name="name" label="Фамилия Имя"></v-text-field>
                <v-text-field name="phone" label="Телефон"></v-text-field>
                <div class="d-flex justify-center">
                    <v-btn type="submit"  color="#F90007" text-color="black" >отправить</v-btn>
                </div>
                
            </v-form>
    </v-col>
</v-row>
</template>
<style scoped>
.reg{
    background: #293128;
    color: #EAEAC3;
}
.title {
  font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);

    text-transform: uppercase;
    font-weight: 600;
}
</style>