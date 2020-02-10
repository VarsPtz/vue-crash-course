<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <h1>Todo application</h1>
    <hr>
    <!--<AddTodo-->
      <!--@add-todo="addTodo"-->
    <!--/>-->
    <!--<hr>-->
    <!--<TodoList-->
      <!--v-bind:todos="todos"-->
      <!--@remove-todo="removeTodo"-->
    <!--/>-->
    <router-view />
  </div>
</template>



<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
