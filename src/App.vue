<template>
  <div id="app">
    <Header />
    <AddTodo />
    <ToDos @del-todo="completeTodo" :todos="todos" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import ToDos from "./components/ToDos.vue";
import Header from "./components/layouts/Header.vue";
import AddTodo from "./components/AddTodo.vue";
export default {
  name: "app",
  methods: {
    completeTodo(id) {
      //console.log("APP received the id", id);
      this.todos = this.todos.filter(item => item.id !== id);
    }
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo 1",
          completed: false
        },
        {
          id: 2,
          title: "Todo 2",
          completed: true
        },
        {
          id: 3,
          title: "Todo 3",
          completed: false
        }
      ]
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
