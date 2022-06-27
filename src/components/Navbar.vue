<template>
  <nav class="main-nav">
    <router-link :to="{ name: 'Home'}" >Projects</router-link>
    <router-link :to="{ name: 'Addproject'}" >Add a New Project</router-link>
  </nav>
</template>

<script>
export default {

}
</script>

<style>
    .main-nav{
        text-align: center;
        margin: 40px auto;
    }
    .main-nav a{
        display:inline-block;
        text-decoration: none;
        margin: 0 10px;
        color: #000000;
        font-size: 20px;

    }
    a.router-link-active{
        background: #00ce99;
        padding: 4px;
        border-radius: 4px;
        transition: 0.1s;
    }
</style>