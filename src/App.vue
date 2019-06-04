<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todo_data" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './/components/layout/Header.vue'
import AddTodo from "./components/AddTodo.vue"
import Todos from "./components/Todos.vue"

export default {
  name: "app",
  components: {
    Header,
    AddTodo,
    Todos
  },
  methods: {
    deleteTodo(id){
      this.todo_data = this.todo_data.filter(todo => todo.id != id);
    },
    addTodo(newTodo){
      this.todo_data.push(newTodo);
    }
  },
  data() {
    return {
      todo_data: [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: true
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        }
      ]
    };
  }
};
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

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover {
  background: #777;
}
</style>
