<script setup>
import { ref } from "vue";
import Avatar from "./AvatarComponent.vue";

const mobileMenuOpen = ref(false);

function toggleMobileMenu() {
  if (mobileMenuOpen.value) {
    const mobileMenu = document.querySelector(".mobile-links");
    mobileMenu?.classList.add("closed");
    setTimeout(() => {
      mobileMenuOpen.value = false;
      mobileMenu?.classList.remove("closed");
    }, 400);
    return;
  }
  mobileMenuOpen.value = true;
}

const links = ["Projects", "Skills", "Resume", "Contact"];
</script>

<template>
  <div class="nav-bar">
    <Avatar />
    <ul class="links">
      <li v-for="link in links" :key="link">
        {{ link }}
      </li>
    </ul>
    <ul v-if="mobileMenuOpen" class="mobile-links">
      <li v-for="link in links" @click="toggleMobileMenu" :key="link">
        {{ link }}
      </li>
    </ul>
    <div @click="toggleMobileMenu" class="menu-icon">
      <vue-feather v-if="mobileMenuOpen" type="x" />
      <vue-feather v-else type="menu" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.nav-bar {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 5rem;
  background-color: transparent;
  color: var(--white-mute);
  width: 100%;
}

.links,
.mobile-links {
  display: flex;
  list-style: none;
  margin-left: auto;

  li {
    position: relative;
    cursor: pointer;
    display: flex;
    justify-content: center;
    width: 5rem;
    margin: 0 0.2rem;
  }
}

.mobile-links {
  position: absolute;
  z-index: 1;
  top: 5rem;
  left: -10%;
  display: none;
  flex-direction: column;
  align-items: center;
  width: 120%;
  height: 100vh;
  animation: enterTopRight 0.4s ease-in-out;
  transform-origin: 100% 0%;
  background: rgba(14 24 42 / 0.8);
  backdrop-filter: blur(5px);

  li {
    margin: 0.5rem 0;
    animation: fadeInFromLeft 0.7s ease-in-out;
  }
}

.mobile-links.closed {
  animation: exitTopRight 0.4s ease-in-out;
}

.links li::after,
.menu-icon::after,
.mobile-links li::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--white-mute);
  border-radius: 0.1rem;
  transition: all 0.3s ease-in-out;
}

.links li:hover::after,
.menu-icon:hover::after,
.mobile-links li:hover::after {
  width: 100%;
}

.menu-icon {
  cursor: pointer;
  display: none;
  margin-top: 0.5rem;

  :hover {
    color: var(--dark-red);
  }
}

@media screen and (max-width: 500px) {
  .links {
    display: none;
  }

  .mobile-links {
    display: flex;
  }

  .menu-icon {
    display: block;
  }
}
</style>
