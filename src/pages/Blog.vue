<script setup>
import { watch, ref } from 'vue';
import { useRoute } from 'vue-router';

const route = useRoute();
const id = ref(route.params.id);

watch(route, () => {
  id.value = route.params.id;
});
</script>

<template>
  <h1>blog page</h1>
  <p>blog id = {{ id }}</p>
</template>
