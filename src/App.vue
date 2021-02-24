<template>
  <main>
    <div class="container">
      <h1>Hello, welcome to the todolist</h1>
      <todo-add :tid="todos.length" @add-todo="addTodo"/>
      <todo-filter :selected="filter" @change-filter="filter = $event"/>
      <todo-list :todos="filteredTodos"/>
    </div>
  </main>
</template>

<script>
import { computed, ref } from 'vue';
import TodoAdd from "./components/TodoAdd.vue";
import TodoFilter from './components/TodoFilter.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    TodoAdd,
    TodoFilter,
    TodoList
  },
  setup(){
    const todos = ref([])
    const addTodo = (todo) => todos.value.push(todo)
    const filter = ref("all")

    const filteredTodos = computed(() => {
      switch(filter.value){
        case "done":
          return todos.value.filter((todo) => todo.completed)
        case "todo":
          return todos.value.filter((todo) => !todo.completed)
        default:
          return todos.value
      }
    })
    return {
      todos,
      addTodo,
      filter,
      filteredTodos
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, "PingFang SC", "Microsoft Yahei", san-serif;
}

main {
  width: 100vw;
  height: 100vh;
  display: grid;
  align-items: center;
  justify-content: center;
  background: rgb(203, 210, 240);
}

.container {
  width: 100%;
  max-width: 600px;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}

</style>
