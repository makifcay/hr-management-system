<template>
  <div class="edit">
    <Navbar/>
    <ApplicantNav/>

    <div class="container text-center">
      <h1>Edit</h1>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import ApplicantNav from "@/components/ApplicantNav.vue";

export default {
  name: "Register",
  components: {
    Navbar,
    ApplicantNav
  }
};
</script>

<style scoped lang="scss">

</style>