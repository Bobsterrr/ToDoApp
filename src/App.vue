<script setup>
</script>

<template>
  <div id='container'>
    <div id='todo-app'>
      <h2>To-Do List</h2>
      <div id='row'>
        <input type='text' id='input-box' placeholder='Add Your Text'>
        <button>Add</button>
      </div>
      <ul id='list-container'>
        <li>Task 1</li>
        <li>Task 2</li>
        <li>Task 3</li>
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
  background: #ff5945;
  font-size: 16px;
  cursor: pointer;
  border-radius: 40px;
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
  font-weight: 14px;
}

ul li {
  list-style: none;
  font-size: 17px;
  padding: 12px 8px 12px 50px;
  user-select: none;
  cursor: pointer;
}
</style>
