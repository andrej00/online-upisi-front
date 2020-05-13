<template>
  <div>
    <nav :class="{change_color: scrollPosition > 20}" class="navbar navbar-expand-lg navbar-dark fixed-top">
      <a href="#" class="navbar-brand"></a>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item href="#">{{navbar_text_1}}</b-nav-item>
          <b-nav-item href="#">{{navbar_text_2}}</b-nav-item>
          <b-nav-item href="#">{{navbar_text_3}}</b-nav-item>
          <b-nav-item href="#">{{navbar_text_4}}</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </nav>
  </div>
</template>

<script>

export default {
  name: "Navbar",
  data: function(){
    return{
      scrollPosition: null,
      navbar_text_1: "NASLOVNICA",
      navbar_text_2: "ODABERI ZNANJE",
      navbar_text_3: "INFORMACIJE",
      navbar_text_4: "RAZEDMENI POSTUPAK",
    }
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }
};
</script>

<style>
.navbar {
  font-family: "Open Sans", sans-serif;
  box-shadow: 0 10px 7px -2px rgba(0, 0, 0, 0.2);
  background-color: #1a428365 !important;
}
.navbar-brand {
  margin: 0px 0px 0px 30px;
}
.navbar-dark .navbar-nav .nav-link {
  color: #fafafa !important;
  margin: 0px 30px 0px 0px;
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
/*promjena navbar boje nakon event scroll*/
.change_color {
  background:#1a4283 !important;
}
</style>