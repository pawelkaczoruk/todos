<template>
  <div>
    <Navbar />
    <Home />
  </div>
</template>

<script>
import Home from './views/Home'
import Navbar from './components/Navbar'

export default {
  name: 'app',
  components: {
    Home,
    Navbar
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
