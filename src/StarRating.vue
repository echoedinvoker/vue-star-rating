<template>
  <div class="container">
    <div class="star-container">
      <slot></slot>
    </div>
    <slot name="msg"></slot>
  </div>
  <div>{{ message }}</div>
</template>

<script setup>
import { computed, defineProps } from 'vue';

const props = defineProps({ rating: Number })

const message = computed(() => props.rating / 4 > 0.8
  ? "Great" : props.rating / 4 < 0.3
    ? "Bad" : "Normal")
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  gap: 16px;
}

.star-container {
  display: flex;
}
</style>

