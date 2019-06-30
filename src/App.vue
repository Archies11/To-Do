<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos_list" v-on:del-todo="deleteItem"/>
  </div>
</template>

<script>
import Header from './components/Layout/Header.vue';
import Todos from './components/Todos.vue';

export default {
  name: 'app',
  components: {
    Todos,
    Header
  },
  data() {
    return {
      todos_list: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteItem(id) {
      this.todos_list = this.todos_list.filter(todo => todo.id!== id);
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
