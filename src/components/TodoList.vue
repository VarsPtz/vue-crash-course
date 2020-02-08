<template>
  <div>
    <ul>
      <!--{{ todos }}-->
      <TodoItem
        v-for="(todo, i) of todos"
        :todo="todo"
        :index="i"
        :key="todo.id"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>
<!--Требование к шаблону - должен быть один корневой элемент. Обычно, div-->

<script>
  import TodoItem from '@/components/TodoItem'
  export default {
    props: ['todos'],
    components: {
        TodoItem
    },
    methods: {
        removeTodo(id) {
            // console.log(id)
          this.$emit('remove-todo', id)
        }
    }
  }
</script>

<!--scoped - стили видны только внутри данного компонента-->
<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>