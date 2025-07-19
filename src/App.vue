<script setup>
import { ref, computed } from 'vue';

const todos = ref([]);
const newTodo = ref('');
const hideCompleted = ref(false);

let id = todos.value.length > 0 ? Math.max(...todos.value.map(todo => todo.id)) + 1 : 1;

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((todo) => !todo.done)
    : todos.value;
});

// Methods
function addTodo() {
  if (newTodo.value.trim() === '') {
    return;
  }
  todos.value.push({
    id: id++,
    text: newTodo.value,
    done: false
  });
  newTodo.value = '';
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}
</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="new todo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button id='todo_deleting' @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}

ul {
  all: unset;
}

li {
  all: unset;
}

</style>
