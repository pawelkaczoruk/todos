<template>
  <div>
    <Navbar />
    <Home 
      :todos="todos" 
      @del-todo="deleteTodo" 
      @add-todo="addTodo"
      @mark-complete="markComplete" />
  </div>
</template>

<script>
import Home from './views/Home'
import Navbar from './components/layout/Navbar'

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
    updateStorage() {
      localStorage.setItem('todos', JSON.stringify(this.todos));
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
      this.todos.forEach((todo, i) => {
        todo.id = i+1;
      });
      this.updateStorage();
    },
    addTodo(todo) {
      todo.id = this.todos.length + 1;
      this.todos = [...this.todos, todo];
      this.updateStorage();
    },
    markComplete(id) {
      this.todos[id-1].completed = !this.todos[id-1].completed;
      this.updateStorage();
    }
  },
  mounted() {
    if(localStorage.todos) {
      this.todos = JSON.parse(localStorage.getItem('todos') || "[]");
    }
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
