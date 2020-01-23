<template>
  <div>
    <form>
      <input type="text" v-model="title" placeholder="To do...">
      <button @click="addTodo">Add todo</button>
    </form>
    
  </div>
</template>

<script>
export default {
  name: 'addTodo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo() {
      event.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
}
</script>

<style lang="scss" scoped>
  form {
    width: 100%;
  }

  button {
    width: 120px;
    height: 34px;
    border: none;
    background: #363434c2;
    font-size: 16px;
    cursor: pointer;
  }

  input[type="text"] {
    color: black;
    width: calc(100% - 120px);
    height: 34px;
    font-size: 16px;
    padding-left: 12px;
  }
</style>