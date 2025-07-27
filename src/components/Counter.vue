<script setup>
import {computed} from 'vue'

const props = defineProps(['newTodo'])

const characterCount = computed(() => {
  return props.newTodo.length
})
</script>

<template>
  <p class='counter'>
    {{characterCount}}/50
  </p>
</template>


