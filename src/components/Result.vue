<script setup>
import { defineProps } from "vue";
import { RouterLink } from "vue-router";

const { numberOfCorrectAnswers, quizQuestionLength } = defineProps([
  "quizQuestionLength",
  "numberOfCorrectAnswers",
]);
</script>
<template>
  <div class="results">
    <p>Your Result...</p>
    <h1>{{ numberOfCorrectAnswers }} / {{ quizQuestionLength }}</h1>
    <RouterLink to="/"><button class="btn-goback">Go Back</button></RouterLink>
  </div>
</template>
<style scoped>
.results {
  text-align: center;
  padding: 100px 0;
}
p {
  font-size: 35px;
}
h1 {
  font-size: 45px;
}
.btn-goback {
  background-color: rgb(100, 116, 110);
  padding: 10px;
  margin-top: 30px;
  font-size: 30px;
  border: none;
  border-radius: 10px;
  color: aliceblue;
  transition: 0.3s;
  cursor: pointer;
}
.btn-goback:hover {
  background-color: rgb(148, 163, 158);
  transition: 0.3s;
}
</style>
