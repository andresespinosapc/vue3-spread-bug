<script setup>
import { watch } from 'vue';
import { useInfiniteQuery } from 'vue-query';

const { data } = useInfiniteQuery('test', () => {
  return { test: 1 };
})

watch(data, newData => {
  if (newData) {
    console.log('Original data', newData);
    console.log('Data with spread', { ...newData });
  }
}, { immediate: true });
</script>

<template></template>
