<template>
  <div id="app">
    <!-- Main App Component -->
    <Http />
    <!-- Footer Component -->
    <Footer />
  </div>
</template>

<script>
import Http from './components/Http.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Http,
    Footer
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
</style>
