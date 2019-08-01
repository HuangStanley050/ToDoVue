<template>
  <div class="todo-item" :class="{ 'is-complete': todo.completed }">
    <p>
      <input type="checkbox" @change="markComplete" />
      <button @click="deleteToDo(todo.id)" class="del">X</button>
      {{ todo.title }}
    </p>
  </div>
</template>
<script>
export default {
  name: "ToDoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
    deleteToDo(id) {
      //console.log(id);
      this.$emit("del-todo", id);
    }
  }
};
</script>
<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
