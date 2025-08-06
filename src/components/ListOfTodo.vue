<script setup>
import {inject} from 'vue'


const {tasks} = inject('todo')

const toggleCheck = (task) => {
  task.checked = !task.checked;
}
</script>

<template>
      <ul>
        <li v-for='task in tasks'
          :key='task.text'
          :class='{checked: task.checked}'
          @click='toggleCheck(task)'>
          {{task.text}}
        </li>
      </ul>
      <p v-if='!tasks.length' id='todo_absenceMessage'>
        You have Nothing To Do
      </p>
</template>

<style>
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

#todo_absenceMessage {
  font-size: 22px;
  font-weight: bold;
  text-align: center;
  color: var(--green);
  margin-top: 15px;
}
</style>
