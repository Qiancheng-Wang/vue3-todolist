<template>
  <div class="todo-list">
      <todo-list-item 
        v-for="todo in todos" 
        :todo-item="todo" 
        :key="todo.id"
        @change-state="todo.completed = $event.target.checked"
      ></todo-list-item>
  </div>
</template>

<script>
import TodoListItem from "./TodoListItem.vue"

export default {
    components: {
        TodoListItem
    },
    props: ["todos"]
}
</script>

<style>
.todo-list {
  display: grid;
  row-gap: 14px;
}
</style>