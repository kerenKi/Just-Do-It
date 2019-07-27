<template>
  <div id="app">
    <Header/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <AddTodo  v-on:add-todo="addTodo"/>

  </div>
</template>

<script>
import Header from './components/Layout/Header'
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter( todo => todo.id != id)
    },

    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  },
  data() {
    return {
      todos:[
        {
          id: 1,
          title: 'Clean the house',
          completed: false
        },
        {
          id: 2,
          title: 'Write some code',
          completed: false
        },
        {
          id: 3,
          title: 'Call Gili',
          completed: false
        }
      ]
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
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
    background: #666;
  }
</style>
