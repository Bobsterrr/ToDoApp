<script setup>
import {ref, computed} from 'vue'

const newTodo = ref('');

const characterCount = computed(() => {
  return newTodo.value.length
})
</script>

<template>
      <p class='counter'>
        {{characterCount}}/50
      </p>
</template>

<style>

</style>
