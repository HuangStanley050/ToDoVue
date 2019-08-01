<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <ToDoItem :todo="todo" />
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
