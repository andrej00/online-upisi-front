<template>
  <div id="app">
    <Navbar/>
    <Landing/>
    <SignInForm />
    <Info />
  </div>
</template>

<script>
import Navbar from './components/Navbar';
import Landing from './components/Landing';
import SignInForm from './components/SignInForm';
import Info from './components/Info'
export default {
  name: "App",
  components: {
    Navbar,
    Landing,
    SignInForm,
    Info
  }
};
</script>

<style>
</style>