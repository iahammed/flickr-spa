<template>
  <div class="hello">
    <nav class="navbar bg-light navbar-light fixed-top">
    <a class="navbar-brand" href="/">BubbleGate-SPA </a>
  </nav>
    <result></result>
  </div>
</template>

<script>
import result from '../components/result.vue'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    result
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
