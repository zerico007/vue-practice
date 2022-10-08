<script setup>
import hi from "../assets/hi.png";
</script>
<template>
  <div class="greeting">
    <div class="wave">
      <span>Hi!</span>
      <img :src="hi" alt="hi" />
    </div>
    <div class="intro">
      <h1>I'm Bavin</h1>
      <h2>Frontend Developer | React | Vue</h2>
    </div>
  </div>
</template>

<style scoped lang="scss">
.greeting {
  margin: 2rem auto;
  background: rgba(255 255 255 / 0.5);
  border: 2px solid rgba(255 255 255 / 0.4);
  display: flex;
  flex-direction: column;
  padding: 1rem;
  border-radius: 0.5rem;
  color: var(--black-soft);
  max-width: 400px;
  width: 70%;
  text-align: center;

  .wave {
    display: flex;
    align-items: center;
    align-self: center;

    img {
      width: 50px;
      height: 50px;
      margin-left: 0.5rem;
      object-fit: cover;
    }
  }

  span,
  h1,
  h2 {
    color: #fff;
    background: linear-gradient(45deg, #20bdff, #a5fecb);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
}
</style>
