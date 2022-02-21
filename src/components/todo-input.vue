<script setup lang="ts">
import { Todo } from "../models/todo";
import { useMainStore } from "../store/index";

const mainStore = useMainStore();

function createTodo() {
  mainStore.createNewTodo({ text: "test", id: "s", isDone: false } as Todo);
}
</script>

<template>
  <input type="text" />
  <button v-on:click="createTodo()">Add</button>
</template>

<style scoped></style>
