<script setup>
import { defineProps } from "vue";
const { questionStatus, barPercentage } = defineProps([
  "questionStatus",
  "barPercentage",
]);
</script>
<template>
  <div>
    <header class="header">
      <h4>Question {{ questionStatus }}</h4>
      <div class="bar">
        <div class="completion" :style="{ width: barPercentage }"></div>
      </div>
    </header>
  </div>
</template>
<style scoped>
header {
  margin-top: 20px;
}
header h4 {
  font-size: 30px;
}
.bar {
  width: 300px;
  height: 50px;
  border: 3px solid rgb(167, 167, 187);
  border-radius: 15px;
}
.completion {
  height: 100%;
  width: 0%;
  background-color: rgb(108, 108, 233);
  border-radius: 12px;
}
</style>
