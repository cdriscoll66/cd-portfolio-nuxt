<script setup lang="ts"></script>

<template>
  <footer>
    <div>© 2023 - Driscoll66.com</div>
  </footer>
</template>

<style scoped lang="scss">
footer {
  z-index: 1;
  position: fixed;
  bottom: 5px;
  font-family: "Henderson Slab", serif;
  text-transform: uppercase;
  font-size: 0.5rem;
  color: var(--color-sailor-boy);
  width: 100%;
  div {
    margin: 0 20px;
    max-width: var(--site-content-width);
    @media screen and (min-width: 1440px) {
      margin: 0 auto;
      padding: 0 20px;
    }
  }
}
</style>
