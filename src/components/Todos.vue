<template>
  <div>
    <div :key="todo.id" v-for="todo in todos">
      <Todo :todo="todo" @del-todo="delTodo" @mark-complete="markComplete" />
    </div>    
  </div>
</template>

<script>
import Todo from './Todo'

export default {
  name: 'Todos',
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    delTodo(id) {
      this.$emit('del-todo', id);
    },
    markComplete(id) {
      this.$emit('mark-complete', id);
    }
  }
}
</script>

<style lang="scss" scoped>

</style>