<script setup>
import { defineProps } from 'vue';
import { RouterLink } from 'vue-router';
const {quizQuestionLength, numberOfCorrectAnswer} = defineProps (['quizQuestionLength','numberOfCorrectAnswer'])
</script>
<template>
    <div class="result-container">
        <p>Your result...</p>        
        <h1>{{numberOfCorrectAnswer}}/{{quizQuestionLength}}</h1>
        <RouterLink to="/" class="home">Go back to Quiz Menu</RouterLink>
    </div>
</template>
<style scoped>

.result-container{
 padding: 0;
 display: flex;
 flex-direction: column;
 align-items: center;
}
.result-container  p{
    font-size: 50px;
    margin: 0;
}
.result-container  h1{
    font-size:100px;
    margin: 0;
}
.home{
    text-decoration: none;
    color: green;
    font-size: 20px;
    text-align: right;
}
</style>