<script setup>
const props = defineProps(['newTodo'])
const emit = defineEmits(['add-todo', 'update-todo'])

function addTodo() {
  emit('add-todo')
}

function updateTodo(event) {
  emit('update-todo', event.target.value)
}
</script>

<template>
  <form
    id='row'
    @submit.prevent='addTodo'
  >
    <input
      :value='newTodo'
      @input='updateTodo'
      id='input-box'
      type='text'
      required
      placeholder='Add Your Text'
      maxlength="50"
    >
    <button>Add</button>
  </form>
</template>

<style>
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
