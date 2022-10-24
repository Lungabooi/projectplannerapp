<template>
  <nav class="main-nav">
    <router-link :to="{name: 'home'}"> Projects</router-link>
    <router-link :to="{name: 'AddProject'}"> Add a new Project</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style>
.main-nav {
  text-align: center;
  margin: 40px;
}
.main-nav a {
  display: inline-block;
  text-decoration: none;
  margin: 0 10px;
  color: grey;
  font-size: 20px;
}

a.router-link-active{
  border-bottom: 2px solid green;
  padding-bottom: 4px ;
}

</style>