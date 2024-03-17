<template>
  <div id="app">
    <HeaderComp />
    <ProjectComp />
    <HomeComp />
    <FooterComp />
    
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import FooterComp from './components/FooterComp.vue'
import ProjectComp from './components/ProjectComp.vue'
import HomeComp from './components/HomeComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    FooterComp,
    ProjectComp,
    HomeComp,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
