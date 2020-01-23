<template>
  <div class="todo-item">
    <div class="wrapper">
      <p>lorem ipsum sit dolor</p>
      <button><div class="remove"></div></button>      
    </div>
  </div>
</template>

<script>
export default {
  name: 'Todo'
}
</script>

<style lang="scss" scoped>
  .todo-item {
    width: 100%;
    height: 48px;
    background: #62929a;
    border-radius: 8px;

    .wrapper {
      height: 100%;
      width: calc(100% - 24px);
      margin: 0 12px;
      display: flex;
      align-items: center;
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
</style>