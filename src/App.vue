<template>
  <Navbar />
  <router-view/>
</template>
<script>
import Navbar from './components/Navbar.vue'

export default{
  components: { Navbar }
}
</script>

<style>
body{
  background-color:rgb(232, 215, 215) ;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 600px;
  margin: 0 auto;
  color: #2c3e50;
  

}

</style>
