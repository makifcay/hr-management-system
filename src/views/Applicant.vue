<template>
  <div class="applicant">
    <Navbar/>
    <div class="container text-center">
      <div class="btn-group" role="group" aria-label="Basic example">
        <router-link class="btn btn-success" router-tag="button" to="/applicant/register">
          Yeni Kayıt
        </router-link>
        <router-link class="btn btn-primary" router-tag="button" to="/applicant/edit">
          Kaydı Düzenle
        </router-link>
        <router-view/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";

export default {
  name: "Applicant",
  components: {
    Navbar
  }
};
</script>

<style scoped lang="scss">
.container {
  margin: 10px auto;
  .btn-group {
    margin: 10px auto;
  }
}
</style>