<template>
  <section>
    <base-card>
      <h2>Submitted Experiences</h2>
      <div>
        <base-button @click="getSurvey">
          Load Submitted Experiences
        </base-button>
      </div>
      <ul>
        <SurveyResult
          v-for="result in results"
          :key="result.id"
          :name="result.name"
          :rating="result.rating"
        />
      </ul>
    </base-card>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import SurveyResult from './SurveyResult.vue';

const results = ref([]);

const getSurvey = () => {
  fetch('https://maximilian-http-ef182-default-rtdb.firebaseio.com/survey.json')
    .then((res) => res.json())
    .then((data) => {
      let result = [];
      for (let i in data) {
        result.push({ id: i, name: data[i].userName, rating: data[i].rating });
      }
      results.value = result;
    });
};
// const props = defineProps({
//   results: {
//     type: Array,
//     default: null,
//   },
// });
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
