<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>


<script>
import Todos from './components/Todos';
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data(){
    return{
      todos:[
        {
          id: 1,
          title: "Program To-Do List",
          completed: false
        },
        {
          id: 2,
          title: "Deploy App",
          completed: false
        },
        {
          id: 3,
          title: "Conquer the world",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<!-- Style from App.vue is global -->
<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
