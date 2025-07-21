<script setup>
import {ref} from 'vue'

const newTodo = ref('');
const tasks = ref([])

function addTodo() {
  tasks.value.push({text: newTodo.value, checked: false})
  newTodo.value = '';
}

const toggleCheck = (task) => {
  task.checked = !task.checked;
}
</script>

<template>
  <div id='container'>
    <div id='todo-app'>
      <h2>To-Do List</h2>
      <div id='row'>
        <input type='text' v-model='newTodo' id='input-box' required placeholder='Add Your Text'>
        <button @click='addTodo'>Add</button>
      </div>
      <ul>
        <li v-for='task in tasks'
          :key='task.text'
          :class='{checked: task.checked}'
          @click='toggleCheck(task)'>
          {{task.text}}
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
  box-sizing: border-box;
}

button{
  border: none;
   outline: none;
  padding: 16px 50px;
  background: #84df84;
  font-size: 16px;
  cursor: pointer;
  border-radius: 40px;
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

#row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: #edeef0;
  border-radius: 30px;
  padding-left: 20px;
  margin-bottom: 25px;
}

input {
  flex: 1;
  border: none;
  background: transparent;
  padding: 10px;
  font-size: 14px;
}

ul li {
  transition: 0.5s;
  list-style: none;
  font-size: 17px;
  padding: 12px 8px 12px 50px;
  user-select: none;
  cursor: pointer;
  position: relative;
}

ul li::before {
  transition: 0.5s;
  content: '';
  position: absolute;
  height: 28px;
  width: 28px;
  border-radius: 50%;
  background-image: url(unchecked.png);
  background-size: cover;
  background-position: center;
  top: 12px;
  left: 8px;
}

ul li.checked {
  transition: 0.5s;
  color: #555;
  text-decoration: line-through;
}

ul li.checked::before {
  transition: 0.5s;
  background-image: url(checked.png);
}
</style>
