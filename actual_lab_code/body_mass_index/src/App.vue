<script setup>
import BMI_Calculator from './components/BMI_Calculator.vue';
import {ref, watch} from 'vue'



//variables that will be passed as props to child
const initialStatement = ref('Check you BMI! Enter your height and weight below.')
const heightStatement = ref('Height in meters: ')
const weightStatement = ref('Weight in Kilograms: ')

//used to display calculated BMI
const displayBMI = ref('')

//function used to process and diplay final BMI
function dipsplayFinalBMI(finalBMI){
    displayBMI.value = `Your BMI is ${finalBMI}`
}

</script>

<template>

      <!--HTML which displays text as well as binding props to values they will recieve-->
<h1>Body Mass Index Calculator</h1>
<BMI_Calculator v-bind:mainStatement="initialStatement"
    v-bind:heightQuestion="heightStatement"
    v-bind:weightQuestion="weightStatement"
    v-on:stats-entered="dipsplayFinalBMI">
</BMI_Calculator>

<p>{{ displayBMI }}</p>

 
</template>

<style scoped>

</style>
