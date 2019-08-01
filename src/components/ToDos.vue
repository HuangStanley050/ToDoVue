<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <ToDoItem :todo="todo" @del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>
<script>
import ToDoItem from "./ToDoItem.vue";
export default {
  name: "ToDos",
  props: ["todos"],
  components: { ToDoItem }
};
</script>
<style scoped></style>
