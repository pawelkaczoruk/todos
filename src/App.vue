<template>
  <div>
    <Navbar />
    <Home :todos="todos" @del-todo="deleteTodo" @add-todo="addTodo" />
  </div>
</template>

<script>
import Home from './views/Home'
import Navbar from './components/layout/Navbar'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Home,
    Navbar
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(() => this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => window.alert(err));
    },
    addTodo(todo) {
      axios.post('https://jsonplaceholder.typicode.com/todos', todo)
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => window.alert(err));
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=7')
      .then(res => this.todos = res.data)
      .catch(err => window.alert(err));
  }
}
</script>

<style lang="scss">
  * {
    @import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');

    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: white;
  }
</style>
