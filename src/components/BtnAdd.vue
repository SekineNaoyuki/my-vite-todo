<script setup>
import BaseBtn from '/src/components/BaseBtn.vue';
const emit = defineEmits(['add-click']);
</script>

<template>
  <BaseBtn color="blue" on-click="emit('add-click')">追加</BaseBtn>
</template>
