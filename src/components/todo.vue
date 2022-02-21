<script setup lang="ts">
const props = defineProps(["todo"]);
</script>

<template>
  <span>{{ props.todo.text }}</span>
</template>

<style scoped></style>
