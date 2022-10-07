<script>
import NavBar from "./components/NavBar.vue";
import GreetingHi from "./components/GreetingHi.vue";

export default {
  name: "App",
  components: {
    NavBar,
    GreetingHi,
  },
};
</script>

<template>
  <div class="main">
    <NavBar />
    <GreetingHi />
  </div>
</template>
