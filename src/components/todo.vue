<script lang="ts" setup>
import { reactive, ref } from "vue";

const todoItem = ref("");
const todoItems = ref<string[]>([]);
const add = () => {
  todoItems.value.push(todoItem.value);
  todoItem.value = "";
};
</script>

<template>
  <div>
    <input id="input" type="text" v-model="todoItem" /><span
      @click="add"
      style="margin-left: 30px"
      >add</span
    >
    <ul>
      <li v-for="todo in todoItems">{{todo}}</li>
    </ul>
  </div>
</template>

<style>
#input {
  display: inline-block;
  width: 300px;
  margin: auto;
  margin-top: 40px;
}
</style>