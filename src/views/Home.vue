<template>
  <div id="home">
    <div class="wrapper">
      <Todo />
    </div>
  </div>
</template>

<script>
import Todo from '../components/Todo'

export default {
  name: 'Home',
  components: {
    Todo
  }
}
</script>

<style lang="scss" scoped>
  #home {
    width: 100vw;
    height: calc(100vh - 62px);
    background: #efecec;
  }

  .wrapper {
    max-width: 1200px;
    padding: 16px 1%;
    margin: 0 auto;
  }
</style>
