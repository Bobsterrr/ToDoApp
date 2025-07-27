<script setup>
import Form from './Form.vue'
import Counter from './Counter.vue'
import ListOfTodo from './ListOfTodo.vue'

defineProps(['tasks', 'newTodo'])
defineEmits(['add-todo', 'update-todo', 'toggle-check'])
</script>

<template>
  <Form
    :newTodo="newTodo"
    @add-todo="$emit('add-todo')"
    @update-todo="$emit('update-todo', $event)"
  />
  <Counter :newTodo="newTodo"/>
  <ListOfTodo
    :tasks="tasks"
    @toggle-check="$emit('toggle-check', $event)"
  />
</template>
