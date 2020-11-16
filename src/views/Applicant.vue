<template>
  <div class="applicant">
    <Navbar/>
    <ApplicantNav/>
    <router-view/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import ApplicantNav from "@/components/ApplicantNav";

export default {
  name: "Applicant",
  components: {
    ApplicantNav,
    Navbar
  }
};
</script>

<style scoped lang="scss">

</style>