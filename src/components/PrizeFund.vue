<script setup>

</script>
<template>
    <v-row class="prize_fund">
        <v-col class="d-flex  align-center justify-end" cols="12" md="6"
         >
            <h1 class="title">Призы</h1>
        </v-col>
        <v-col  cols="12" md="6">

            <div class="fund">
                <div class="red">
                    Первое место - 10 000 руб.
                </div>
                <div>
                    Второе место - 5 000 руб.
                </div>
                <div>
                    Третье место - 3 000 руб.
                </div>
                <div class="red">
                    Выбор спонсора - 2 000 руб.
                </div>
            </div>


        </v-col>
    </v-row>
</template>
<style scoped>
.prize_fund{
    background: #EAEAC3;
}
.red {
    color: #F90007;
}
.title {
    clip-path: polygon(0 100%, 0 0, 100% 50%);
    background-color: #F90007;
    width: 70%;
    padding: 20px;
    font-size: clamp(1.25rem, 0.7143rem + 1.7143vw, 2rem);
    color: #EAEAC3;
    text-transform: uppercase;
    font-weight: 600;
}
.fund{
    clip-path: polygon(7% 0, 75% 0, 100% 100%, 0% 100%);
    background-color: #000;
  
    padding: 20px;
    padding-left: 20%;
    font-size: clamp(0.75rem, 0.4821rem + 0.8571vw, 1.125rem);
    color: #EAEAC3;
    text-transform: uppercase;
    font-weight: 600;
}
</style>