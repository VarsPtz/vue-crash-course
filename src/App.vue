<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->

    <h1>Todo application</h1>
    <AddTodo
      @add-todo="addTodo"
    />
    <hr>
    <TodoList
      v-bind:todos="todos"
      @remove-todo="removeTodo"
    />
  </div>
</template>

<script>
  // @ всегда указывает в папку /src
  // импортируем компонент
import TodoList from '@/components/TodoList'
import AddTodo from '@/components/AddTodo'
// import HelloWorld from './components/HelloWorld.vue'


  // регистрируем компонент TodoList
  // TodoList: TodoList   если ключ и значение совпадают, то ключ можно не указывать => TodoList
export default {
  name: 'app',
  data() {
    return {
      todos: [
        // {id: 1, title: 'Купить хлеб', completed: false},
        // {id: 2, title: 'Купить масло', completed: false},
        // {id: 3, title: 'Купить пиво', completed: false}
      ]
    }
  },
  mounted() {
      fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
          .then(response => response.json())
          // .then(json => console.log(json))
          .then(json => {
              this.todos = json
          })
  },
  methods: {
    removeTodo(id) {
        this.todos = this.todos.filter(t => t.id !==id)
    },
    addTodo(todo) {
        this.todos.push(todo)
    }
  },
  components: {
    // HelloWorld
    TodoList,
    AddTodo
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
