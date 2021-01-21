<template>
  <div id="app">
    <Convertion />
    
  </div>
</template>

<script>
import Convertion from './components/Convertion.vue'

export default {
  name: 'App',
  components: {
    Convertion   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
