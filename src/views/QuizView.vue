<script setup>
import Question from "../components/Question.vue"
import QuestionHeader from "../components/QuestionHeader.vue"
import { useRoute } from "vue-router"
import { ref, computed } from "vue";
import quizes from "../data/quizes.json"
    const route = useRoute()
    const quizId = parseInt(route.params.id)
    const quiz = quizes.find(q => q.id === quizId)
    const currentQuestionIndex = ref(0)
    const numberOfCorrectAnswer = ref(0)
    const questionStatus = computed(() =>`${currentQuestionIndex.value}/${quiz.questions.length}`)
    const barPercent = computed(() => `${currentQuestionIndex.value/quiz.questions.length * 100}%`)   
    const onSelectedOption = (isCorrect) => {
        if(isCorrect){
            numberOfCorrectAnswer.value++
        }
        currentQuestionIndex.value++
    }
</script>
<template>
<div>    
    {{ numberOfCorrectAnswer }}
    <QuestionHeader :currentQuestion="questionStatus" :barPercent="barPercent"/>
    <Question :question="quiz.questions[currentQuestionIndex]" @selectOption="onSelectedOption"/>    
</div>
</template>

