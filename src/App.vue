<script setup>
</script>

<template>
  <div id='container'>
    <div id='todo-app'>
      <h2>To-Do List</h2>
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

#container {
  width: 100%;
  min-height: 100vh;
  background: black;
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
