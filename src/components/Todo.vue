<template>
  <div class="todo-item" :class="{'is-complete':todo.completed}">
    <div class="wrapper">
      <input :checked="todo.completed" type="checkbox" @change="markComplete">
      <p>{{ todo.title }}</p>
      <button @click="$emit('del-todo', todo.id)"><div class="remove"></div></button>      
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: ['todo'],
  methods: {
    markComplete() {
      this.$emit('mark-complete', this.todo.id);
    },

    removeTodo() {

    }
  }
}
</script>

<style lang="scss" scoped>
  .todo-item {
    width: 100%;
    min-height: 48px;
    background: #62929a;
    border-radius: 8px;
    margin-bottom: 12px;
    padding: 12px 0;

    input[type="checkbox"] {
      margin-right: 10px;
      transform: scale(1.2);
    }

    .wrapper {
      height: 100%;
      width: calc(100% - 24px);
      margin: 0 12px;
      display: flex;
      align-items: center;
    }

    p {
      width: calc(100% - 73.6px);
    }
  }
  
  button {
    margin-left: auto;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: none;
    background: #4D7B82;
    cursor: pointer;
    
    .remove {
      width: 80%;
      border-radius: 4px;
      height: 4px;
      margin: 0 auto;
      background: white;
    }
  }

  .is-complete {
    background: #62929aa9;
    text-decoration: line-through;

    button {
      background: #4D7B82a2;
    }
  }
</style>