<template>
  <div id="app">
    <Navbar/>
    <Landing/>
    <SignInForm />
  </div>
</template>

<script>
import Navbar from './components/Navbar';
import Landing from './components/Landing';
import SignInForm from './components/SignInForm';
export default {
  name: "App",
  components: {
    Navbar,
    Landing,
    SignInForm
  }
};
</script>

<style>
</style>