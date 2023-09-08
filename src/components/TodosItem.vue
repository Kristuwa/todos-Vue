<template>
  <div class="item">
    <p>{{ todo.todoText }}</p>
    <button class="delete-btn" type="button" @click="$emit('remove', todo)">
      X
    </button>
  </div>
</template>

<script>
export default {
  name: "TodosItem",
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scroped>
.item {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
}

.delete-btn {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #252121;
  width: 30px;
  padding: 5px;
  font-weight: 600;
  background-color: transparent;
  border: 1px solid #252121;
  border-radius: 15px;
  transition: color 250ms linear, background-color 250ms linear;
}

.delete-btn:hover,
.delete-btn:focus {
  background-color: #a1a1a1;
  color: #ffffff;
}

.icon {
  display: inline-block;
  width: 1em;
  height: 1em;
  stroke-width: 0;
  stroke: currentColor;
  fill: currentColor;
}
</style>
