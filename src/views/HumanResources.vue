<template>
  <div class="hr">
    <Navbar/>
    <h1>İK Sayfası</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";

export default {
  name: "HumanResources",
  components: {
    Navbar
  }
};
</script>
