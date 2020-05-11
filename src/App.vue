<template>
  <div id="app">
    <Navbar/>
    <Landing/>
    
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Landing from './components/Landing'

export default {
  name: "App",
  components: {
    Navbar,
    Landing
  }
};
</script>

<style>

</style>