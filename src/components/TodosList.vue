<template>
  <div class="list">
    <h2 class="title">List of your todos</h2>
    <p class="bottom-text" v-if="todos.length === 0">
      Your list is empty, add your first task!!
    </p>
    <div v-if="todos.length > 0">
      <todos-item
        :todo="todo"
        v-for="todo in todos"
        :key="todo.id"
        @remove="$emit('remove', todo)"
      />
    </div>
  </div>
</template>

<script>
import TodosItem from "./TodosItem.vue";

export default {
  name: "TodosList",
  components: { TodosItem },
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.list {
  width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.title {
  font-size: 32px;
  text-align: center;
  margin-bottom: 16px;
  color: #1f1f84;
}

.bottom-text {
  font-size: 24px;
  text-align: center;
  color: #3d3a3a;
}
</style>
