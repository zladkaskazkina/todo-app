<template>
  <div id="app">
    <header>
      <h1 class="title">VUEJS ToDo</h1>
    </header>
    <div class="todo-frame">
      <router-view />
    </div>
  </div>
</template>

<script>

export default { 
  
}
</script>

<style>
* {
  margin: 0;
}

.todo-frame {
  position: relative;
  overflow: hidden;
}
header {
  background: #001f3f;
  padding: 10px 20px;
}
.title {
  color: #fff;
  margin: 0;
  font-size: 1em;
  text-transform: uppercase;
}
</style>
