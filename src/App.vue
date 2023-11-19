<template>
  <StarRating :rating="rating">
    <StarItem v-for="index in [0, 1, 2, 3, 4]" :key="index" :full="rating > index" @click="setRating(index + 1)" />
    <template v-slot:msg>
      <p>{{ rating || '' }}</p>
    </template>
  </StarRating>
</template>
<script setup>
import { ref } from 'vue';
import StarRating from './StarRating.vue';
import StarItem from './StarItem.vue';

const rating = ref(0);
const setRating = value => rating.value = value 
</script>
