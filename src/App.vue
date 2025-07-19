<script setup>
import {ref} from 'vue'

const count = ref(0);

</script>

<template>
  <h1>To Do List</h1>
  <input placeholder="Make New ToDo">
  <button>Add Todo</button>
  <button @click='count++'>Count is {{count}}</button>
</template>

<style scoped>
h1 {
  text-align: center;
  font-weight: bold;
  color: white
}

</style>
