<template>
  <li>
    <p>
      <span class="highlight">{{ props.name }}</span> rated the learning
      experience <span :class="ratingClass">{{ props.rating }}</span
      >.
    </p>
  </li>
</template>

<script setup>
import { computed } from 'vue';
const props = defineProps({
  name: {
    type: String,
  },
  rating: {
    type: String,
  },
});

const ratingClass = computed(() => {
  return 'highlight rating--' + props.rating;
});
</script>

<style scoped>
li {
  margin: 1rem 0;
  border: 1px solid #ccc;
  padding: 1rem;
}

h3,
p {
  font-size: 1rem;
  margin: 0.5rem 0;
}

.highlight {
  font-weight: bold;
}

.rating--poor {
  color: #b80056;
}

.rating--average {
  color: #330075;
}

.rating--great {
  color: #008327;
}
</style>
