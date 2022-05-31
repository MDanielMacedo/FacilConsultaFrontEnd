<template>
  <div id="app">
    <Pagina1 />
    <Pagina2 />
  </div>
</template>

<script>
  import Pagina1 from './components/Pagina1.vue'
import Pagina2 from './components/Pagina2.vue'
 
  export default {
    name: 'App',
    components: {
    Pagina1,
    Pagina2
}
  }
</script>

<style scoped>
  #app {
    font-family: 'Open Sans', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
