<template>
  <div id="nav">
    {{info}}
  </div>
  <router-view/>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('')
      .then(response => (this.info = response.data))
  }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
