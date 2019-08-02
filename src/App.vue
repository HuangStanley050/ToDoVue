<template>
  <div id="app">
    <Header />
    <AddTodo @add-todo="addTodo" />
    <ToDos @del-todo="completeTodo" :todos="todos" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import ToDos from "./components/ToDos.vue";
import Header from "./components/layouts/Header.vue";
import AddTodo from "./components/AddTodo.vue";
import axios from "axios";
export default {
  name: "app",
  async created() {
    let result = await axios.get("https://jsonplaceholder.typicode.com/todos");
    this.todos = result.data;
    //console.log(result.data);
  },
  methods: {
    completeTodo(id) {
      //console.log("APP received the id", id);
      this.todos = this.todos.filter(item => item.id !== id);
    },
    addTodo(todo) {
      this.todos = [...this.todos, todo];
    }
  },
  data() {
    return {
      todos: []
    };
  },

  components: {
    AddTodo,
    ToDos,
    Header
    //HelloWorld
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #666;
}
</style>
