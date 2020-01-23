<template>

  <div id="home">
    <AddTodo @add-todo="addTodo" />
    <div class="wrapper">
      <Todos :todos="todos" @del-todo="delTodo" />
    </div>
  </div>

</template>

<script>
import Todos from '../components/Todos'
import AddTodo from '../components/addTodo'

export default {
  name: 'Home',
  props: ['todos'],
  components: {
    Todos,
    AddTodo
  },
  methods: {
    delTodo(id) {
      this.$emit('del-todo', id);
    },
    addTodo(todo) {
      this.$emit('add-todo', todo);
    }
  }
}
</script>

<style lang="scss" scoped>
  #home {
    width: 100%;
    height: calc(100vh - 62px);
    background: #efecec;
  }

  .wrapper {
    max-width: 1200px;
    padding: 12px 1%;
    margin: 0 auto;
  }
</style>
