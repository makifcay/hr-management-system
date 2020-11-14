<template>
  <div id="navbar">
    <b-navbar toggleable="lg" type="dark" variant="primary">
      <b-navbar-brand href="#">İK Yönetim Sistemi</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <router-link class="nav-link" router-tag="b-nav-item" to="/">Ana Sayfa</router-link>
          <router-link class="nav-link" router-tag="b-nav-item" to="/applicant">Aday</router-link>
          <router-link class="nav-link" router-tag="b-nav-item" to="/hr">İK</router-link>
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

<style scoped>

</style>
