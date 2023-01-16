<script setup lang="ts"></script>

<template>
  <div class="overlay-menu">
    <div class="menu-container">
      <NuxtLink to="/work">Work</NuxtLink>
      <NuxtLink to="/styleguide">About</NuxtLink>
    </div>
  </div>
</template>

<style scoped lang="scss">
.overlay-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: var(--color-old-lace);
  color: var(--color-maniac-mansion);
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
}

.menu-container {
  display: flex;
  flex-flow: column nowrap;
  a {
    padding-top: 1rem;
  }

}
</style>
