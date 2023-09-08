<template>
  <div class="app">
    <h1 class="title">Todo list</h1>
    <form-input-todo @create="onSubmitData" />
    <todos-list :todos="todos" @remove="onRemoveTodo" />
  </div>
</template>

<script>
import FormInputTodo from "./components/FormInputTodo.vue";
import TodosList from "./components/TodosList.vue";

export default {
  components: { FormInputTodo, TodosList },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    onSubmitData(formData) {
      if (formData && formData.todoText) {
        const newPost = {
          id: Date.now().toString(),
          todoText: formData.todoText,
          isCompleted: false,
        };
        this.todos.push(newPost);
      }
    },
    onRemoveTodo(todo) {
      this.todos = this.todos.filter((item) => item.id !== todo.id);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  font-family: sans-serif;
}

.app {
  padding: 30px;
}

.title {
  font-size: 36px;
  text-align: center;
  margin-bottom: 16px;
  color: #1f1f84;
}
</style>
