<template>
  <div class="home">
    <Landing />
    <SignInForm />
    <Info />
  </div>
</template>

<script>
import Landing from '../components/Landing'
import SignInForm from '../components/SignInForm'
import Info from '../components/Info'

export default {
  name: 'Home',
  components: {
    Landing,
    SignInForm,
    Info
  }
}
</script>
