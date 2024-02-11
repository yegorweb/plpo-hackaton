<script setup>
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
    </v-col>
</v-row></template>
<style scoped>
</style>