<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { onMounted, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import TodoInput from "./components/todo-input.vue";
import todoVue from "./components/todo.vue";
import { Todo } from "./models/todo";
import { useMainStore } from "./store/index";

const todos = ref<Todo[]>([]);

const mainStore = useMainStore();

onMounted(() => {
  todos.value = mainStore.todos;
});
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  <TodoInput></TodoInput>
  <div v-for="(todo, index) in todos" :key="index">
    <todoVue :todo="todo"></todoVue>
    <span>{{ todo.text }}</span>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
