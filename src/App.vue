<template>
  <div id="app">
    <MainWrapper/>
  </div>
</template>

<script>
import MainWrapper from './components/MainWrapper.vue'

export default {
  name: 'App',
  components: {
    MainWrapper
  }
}
</script>

<style lang="scss">
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
