<template>
  <div id="app">
    <CustomTemplate />
  </div>
</template>

<script>
import CustomTemplate from './components/CustomTemplate.vue'

export default {
  name: 'app',
  components: {
    CustomTemplate
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
