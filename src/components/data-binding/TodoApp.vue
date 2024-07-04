<template>
  <div id="app">
    <h1>Todo App</h1>
    <input
      v-model="inputValue"
      placeholder="Enter a todo"
      @keyup.enter="addTodo"
    />
    <button @click="addTodo">Add Todo</button>
    <TodoList :todos="todos" @delete-todo="deleteTodo" />
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";

export default {
  name: "TodoApp",
  components: {
    TodoList,
  },
  data() {
    return {
      inputValue: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      if (this.inputValue.trim()) {
        this.todos.push({ id: Date.now(), text: this.inputValue });
        this.inputValue = "";
      }
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
