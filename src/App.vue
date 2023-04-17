<template>
  <LearningSurvey />
  <UserExperiences />
</template>

<script setup>
// import { ref } from 'vue';
import LearningSurvey from './components/survey/LearningSurvey.vue';
import UserExperiences from './components/survey/UserExperiences.vue';

// const savedSurveyResults = ref([]);

// const storeSurvey = (data) => {
//   const surveyResult = {
//     name: data.userName,
//     rating: data.rating,
//     id: new Date().toISOString(),
//   };
//   savedSurveyResults.value.push(surveyResult);
//   console.log(surveyResult);
// };
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
