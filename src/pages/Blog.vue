<script setup>
import { watch, ref } from 'vue';
import { useRoute } from 'vue-router';

const route = useRoute();
const id = ref(route.params.id);
const posts = ref([]);

const fetchData = async () => {
  const response = await fetch('https://jsonplaceholder.typicode.com/posts');
  posts.value = await response.json();
};
fetchData();

watch(route, () => {
  id.value = route.params.id;
});
</script>

<template>
  <ul>
    <li v-for="post in posts" :key="posts.id">
      {{ post.id }}
      <router-link :to="`/blog/${post.id}`"> {{ post.title }}</router-link>
    </li>
  </ul>
</template>

<style>
ul {
  margin-top: 12px;
}
li {
  margin-bottom: 8px;
  border: 1px solod #ccc;
  padding: 8px;
}
li:hover {
  background-color: #eee;
}
</style>
