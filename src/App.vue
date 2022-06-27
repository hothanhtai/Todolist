<template>
 <title-vue></title-vue>
  <navbar></navbar>
 <router-view></router-view>
</template>
<script>
import Navbar from "./components/Navbar.vue"
import TitleVue from "./components/Title.vue"


export default{
    
    components: { Navbar ,TitleVue}
}
</script>
<style>
body{
  color: #f2f2f2;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 600px;
  margin: 150px auto;
  color: #555;
}
</style>
