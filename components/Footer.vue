<script setup lang="ts"></script>

<template>
  <footer>
    <div>© 2023 - Driscoll66.com</div>
  </footer>
</template>

<style scoped lang="scss">
footer {
  z-index: 1;
  position: absolute;
  bottom: 16px;
  width: 100%;
  font-family: "Henderson Slab", serif;
  text-transform: uppercase;
  font-size: 0.5rem;
  color: var(--color-sailor-boy);
  padding-bottom: 0;
  div {
    margin: 0 auto;
    max-width: var(--site-container-width);
    width: 100%;
    margin-bottom: 0;
  }
}
</style>
