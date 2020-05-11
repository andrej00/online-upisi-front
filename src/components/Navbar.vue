<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info" fixed="top">
      <b-navbar-brand href="#">Online upisi</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="#">Naslovnica</b-nav-item>
          <b-nav-item href="#">Forma za upis</b-nav-item>
          <b-nav-item href="#">Informacije</b-nav-item>
          <b-nav-item href="#">Razedbeni postupak</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style>
.navbar {
  transition: 1s;
  font-family: "Open Sans", sans-serif;
  box-shadow: 0 10px 7px -2px rgba(0, 0, 0, 0.2);
}
.navbar-brand {
  margin: 0px 0px 0px 30px;
}
.navbar.navbar-dark.bg-info {
  background-color: #1a42837a !important;
}
.navbar-dark .navbar-nav .nav-link {
  color: white !important;
  margin: 0px 37px 0px 0px;
  font-weight: 500;
}
.navbar-dark .navbar-nav .nav-link::after {
  content: "";
  display: block;
  width: 0;
  height: 3px;
  background: white;
  transition: width 0.3s;
}
.navbar-dark .navbar-nav .nav-link:hover::after {
  width: 100%;
  transition: width 0.6s;
}
</style>