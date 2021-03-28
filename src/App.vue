<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class="container">
    <PageHome msg="Bem vindo ao seu App Vue.js"/>
  </div>
</template>

<script>
import PageHome from './components/PageHome.vue'

export default {
  name: 'App',
  components: {
    PageHome
  }
}
</script>

<style>
 @import "assets/style.css"
</style>
