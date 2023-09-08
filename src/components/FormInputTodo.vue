<template>
  <form @submit.prevent="onSubmitData" class="form">
    <div class="input-container">
      <label for="name">Enter your todo:</label>
      <input
        type="text"
        id="name"
        name="name"
        v-model="formData.todoText"
        placeholder="Todo text..."
        required
      />
    </div>

    <button type="submit" class="btn">Add todo</button>
  </form>
</template>

<script>
export default {
  name: "FormInputTodo",
  components: {},
  data() {
    return {
      formData: {
        todoText: "",
      },
    };
  },
  methods: {
    onSubmitData() {
      this.$emit("create", this.formData);
      this.formData = {
        todoText: "",
      };
    },
  },
};
</script>

<style scoped>
.form {
  width: 800px;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 30px;
  padding: 30px;
  border: 2px solid #a1a1a1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.input-container {
  margin-right: 20px;
}

.input-container label {
  margin-right: 20px;
}

.input-container input {
  width: 400px;
  height: 40px;
  padding: 10px;
}

.btn {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #252121;
  background-color: transparent;
  width: 100px;
  height: 30px;
  font: inherit;
  font-weight: 500;
  border-radius: 10px;
  transition: color 250ms linear, background-color 250ms linear;
}

.btn:hover,
.btn:focus {
  background-color: #a1a1a1;
  color: #ffffff;
}
</style>
