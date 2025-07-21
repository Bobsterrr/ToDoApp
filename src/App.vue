<script setup>
import {ref, computed} from 'vue'
import Todo from './components/Todo.vue'

const newTodo = ref('');
const tasks = ref([])




const toggleCheck = (task) => {
  task.checked = !task.checked;
}
</script>

<template>
  <div id='container'>
    <div id='todo-app'>
      <h2>To-Do List</h2>
      <Todo/>
      <p v-if='!tasks.length' id='todo_absenceMessage'>
        You have Nothing To Do
      </p>
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



#todo_absenceMessage {
  font-size: 22px;
  font-weight: bold;
  text-align: center;
  color: var(--green);
  margin-top: 15px;
}

</style>
