<template>
  <div>
    <form @submit.prevent="addTodo">
      <input
        v-model="title"
        type="text"
        name="title"
        placeholder="Add todo..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>
<script>
import uuid from "uuid";
export default {
  name: "AddTodo",
  methods: {
    addTodo() {
      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  },
  data() {
    return {
      title: ""
    };
  }
};
</script>
<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>
