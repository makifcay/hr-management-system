<template>
  <div>
    <b-nav tabs fill>
      <b-nav-item to="/applicant/register">Yeni Kayıt</b-nav-item>
      <b-nav-item to="/applicant/edit">Kaydı Düzenle</b-nav-item>
    </b-nav>
    <router-view/>
  </div>

</template>

<script>
export default {
name: "ApplicantNav"
}
</script>

<style scoped>
div {
  margin-top: 10px;
}
</style>