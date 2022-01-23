<script lang="ts" setup>
import { reactive, ref } from "vue";

const todoItem = ref("");
const todoItems = ref<string[]>([]);
const add = () => {
  console.log(todoItem.value);
  todoItems.value.push(todoItem.value);
  todoItem.value = "";
};
</script>

<template>
  <div class="mx-auto mt-10 w-6/12">
    <input class="w-6/12 border-2 border-slate-800" v-model="todoItem" /><span
      class="ml-3"
      @click="add"
      >add</span
    >
    <ul>
      <li class="mt-4" v-for="todo in todoItems">
        <span>・</span>{{ todo }}<span class="ml-16 text-lg-h3">×</span>
      </li>
    </ul>
  </div>
</template>
