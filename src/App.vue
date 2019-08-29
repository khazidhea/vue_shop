<template>
  <div>
    <NavBar></NavBar>
    <div class="container">
      <Home></Home>
    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Home from './components/Home.vue'

export default {
  name: 'app',
  components: {
    NavBar, Home
  }
}
</script>
