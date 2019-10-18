<template>
  <div id="app">
    <Header />
    <AddTodoForm v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import AddTodoForm from './components/AddTodoForm';
import Header from './components/layout/Header';
import Todos from './components/Todos';

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodoForm
  },
  data() {
    return {
      todos : [
        {
          id: 1,
          title: 'Todo 1',
          completed: false
        },
        {
          id: 2,
          title: 'Todo 2',
          completed: true
        },
        {
          id: 3,
          title: 'Todo 3',
          completed: true
        }
      ]
    }
  },
  methods : {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id)
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
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
