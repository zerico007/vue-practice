<script setup>
import NavBar from "./components/NavBar.vue";
import GreetingHi from "./components/GreetingHi.vue";
import { useCounterStore } from "./stores/counter";

const store = useCounterStore();
</script>

<template>
  <div class="main">
    <NavBar />
    <GreetingHi />
    <button @click="store.increment">
      The count is now: {{ store.count }}
    </button>
  </div>
</template>
