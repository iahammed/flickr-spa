<template>
  <div id="app">
    <HomeView />
  </div>
</template>

<script>
import HomeView from './components/home.vue'
export default {
  name: 'app',
  components: {
    HomeView
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
@import'~bootstrap/dist/css/bootstrap.css'
</style>
