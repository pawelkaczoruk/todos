<template>
  <nav>
    <h1>ToDo</h1>
  </nav>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>

<style lang="scss" scoped>
  nav {
    height: 62px;
    width: 100%;
    background: #363434;
    box-shadow: 0 2px 4px #3634347e;
  }

  h1 {
    color: white;
    text-align: center;
    line-height: 62px;
  }
</style>