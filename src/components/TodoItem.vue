<template>
  <li>
    Todo item 1
  </li>
</template>

<script>
  export default {
    props: {
      todo: {
        type: Object,
        required: true
      }
    }
  }
</script>