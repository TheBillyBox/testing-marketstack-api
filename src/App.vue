<template>
  <div id="nav">
     <ul>
       <li v-for="data in info" v-bind:key="data">
         {{data.close}} dia {{data.date}} símbolo {{data.symbol}}
       </li>
     </ul>
  </div>
  <router-view/>
</template>
<script>
import axios from 'axios'

export default {
  data () {
    return {
      info: null,
    }
  },
  
  mounted () {
    axios.get('')
      .then(response => (this.info = response.data.data))
      .catch(err => (console.log(err)))
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
