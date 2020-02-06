<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <h1>Todo application</h1>
    <hr>
    <TodoList
      v-bind:todos="todos"
    />
  </div>
</template>

<script>
  // @ всегда указывает в папку /src
  // импортируем компонент
import TodoList from '@/components/TodoList'
// import HelloWorld from './components/HelloWorld.vue'

  // регистрируем компонент TodoList
  // TodoList: TodoList   если ключ и значение совпадают, то ключ можно не указывать => TodoList
export default {
  name: 'app',
  data() {
    return {
      todos: [
        {id: 1, title: 'Купить хлеб', completed: false},
        {id: 2, title: 'Купить масло', completed: false},
        {id: 3, title: 'Купить пиво', completed: false}
      ]
    }
  },
  components: {
    // HelloWorld
    TodoList
  }
}
</script>

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
