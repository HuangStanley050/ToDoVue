<template>
  <div id="app">
    <ToDos :todos="todos" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import ToDos from "./components/ToDos.vue";
export default {
  name: "app",
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
    ToDos
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
</style>
