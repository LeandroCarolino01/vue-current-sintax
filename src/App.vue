<template>
  <div id="app">
    <Header />
   <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
   
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';



export default {
  name: 'app',
  components: {
    Header,
    Todos
  },
  data(){
    return {
      todos: [
        {
          id:1,
          title: "todo one",
          completed: true
        },
        {
          id:2,
          title: "todo two",
          completed: false
        },
         {
          id:3,
          title: "todo three",
          completed: false
        }


      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica;
  line-height: 1.4;
}
</style>
