<template>
  <div>
    <ul>
        <!--{{ todos }}-->
      <TodoItem
        v-for="todo of todos"
        v-bind:todo="todo"
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
    }
  }
</script>