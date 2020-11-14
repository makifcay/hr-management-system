<template>
  <div class="home">
    <div class="container text-center">
      <h3>İnsan Kaynakları Yönetim Sistemi</h3>
      <div class="btn-group-vertical">
        <router-link class="btn btn-primary" router-tag="button" to="/applicant">
          Aday Girişi
        </router-link>

        <router-link class="btn btn-secondary" router-tag="button" to="/hr">
          İK Girişi
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>

</script>

<style scoped>
.container .btn-group-vertical {
}

h3 {
  margin-top: 50px;
  margin-bottom: 50px;
}
</style>