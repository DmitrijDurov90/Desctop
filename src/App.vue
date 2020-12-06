<template>
  <div id="app">
    <h1>Todo aplicashen !</h1>
    <add 
    @add-todo='addTodo' 
    />
    <hr>
    <TodoList 
    v-bind:todos="todos"
    @remuve-todo="removeTodo"
    />
    
  </div>
</template>

<script>
import add from '@/components/add'
import TodoList from '@/components/TodoList'

export default {
  name: 'App',
  data(){
    return { 
      todos:[
        {id: 1, title: 'купить хлеб', completed: false},
        {id: 2, title: 'купить масло', completed: false},
        {id: 3, title: 'купить пиво', completed: false}
      ]
    }
  },
  methods: {
    removeTodo(id) {
       this.todos = this.todos.filter(t => t.id !== id)
      
    },
    addTodo(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoList,
    add,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
