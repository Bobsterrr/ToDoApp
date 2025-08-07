<script setup>
import {ref, provide} from 'vue'
import Form from './components/Form.vue'
import ListOfTodo from './components/ListOfTodo.vue'

const tasks = ref([])
const newTodo = ref('')

provide ('todo', {
  newTodo,
  tasks
})

</script>

<template>
  <div id='container'>
    <div id='todo-app'>
      <h2>To-Do List</h2>
      <Form/>
      <ListOfTodo/>
    </div>
  </div>
</template>

<style>
:root {
  --green: #84df84;
}

*{
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
  box-sizing: border-box;
}

#container {
  width: 100%;
  min-height: 100vh;
  background: #232323;
  padding: 10px;
}

#todo-app {
  width: 100%;
  max-width: 540px;
  background: #fff;
  margin: 100px auto 20px;
  padding: 40px 30px 70px;
  border-radius: 10px;
  color: black;
}

#todo-app h2 {
  color: #002765;
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}
</style>
