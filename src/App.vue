<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
export default {
  name: 'app',
  components: {
    Todos
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter( todo => todo.id != id)
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

</style>
