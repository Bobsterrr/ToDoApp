<script setup>
import {computed, inject} from 'vue'

const {newTodo, tasks} = inject('todo')

function addTodo() {
  tasks.value.push({text: newTodo.value, checked: false})
  newTodo.value = '';
}

const characterCount = computed(() => {
  return newTodo.value.length
})
</script>

<template>
      <form
        id='row'
        @submit.prevent='addTodo'
      >
        <input
          v-model='newTodo'
          id='input-box'
          type='text'
          required
          placeholder='Add Your Text'
          maxlength='50'
        >
        <button>Add</button>
      </form>
      <p class='counter'>
        {{characterCount}}/50
      </p>
</template>

<style scoped>
button{
  border: none;
  outline: none;
  padding: 16px 50px;
  background: var(--green);
  font-size: 16px;
  cursor: pointer;
  border-radius: 40px;
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
</style>
