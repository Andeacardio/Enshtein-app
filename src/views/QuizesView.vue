<script setup>
import q from "../assets/data/quizes.json";
import { ref, watch } from "vue";
import Card from "../components/Card.vue";

const quizes = ref(q);
const search = ref("");
watch(search, () => {
  quizes.value = q.filter((quiz) =>
    quiz.name.toLowerCase().includes(search.value.toLowerCase())
  );
});
</script>

<template>
  <div>
    <header class="header">
      <div class="header-left">
        <h1>App for young Einsteins</h1>
        <input v-model.trim="search" type="text" placeholder="Search..." />
      </div>
      <div class="header-rid">
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHw2VhjY2gLlpYqDvgbPr5lciYnS2HL4qvGQ&usqp=CAU"
          alt=""
        />
      </div>
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
      <!-- <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img :src="quiz.img" alt="img" />
        <div class="card-text">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div> -->
    </div>
  </div>
</template>
<style scoped>
.header {
  margin: 10px;
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-radius: 10px;
  background-color: rgb(255, 221, 127);
}

.header h1 {
  font-weight: bold;
  margin-right: 30px;
}
header input {
  border: none;
  background-color: rgba(255, 255, 255, 0.836);
  padding: 10px;
  border-radius: 5px;
}
.header-left input {
  margin-left: 10%;
  width: 250px;
}
.header-rid img {
  border-radius: 50%;
  height: 50px;
}

.options-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 40px;
}
/* Card */
</style>
