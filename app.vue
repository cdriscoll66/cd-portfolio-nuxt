<script setup lang="ts">

const router = useRouter()

router.afterEach((to, from, next) => {
  state.menuOpen = false
  next
})


useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk
      ? `${titleChunk} - Conor Driscoll - JS Dev`
      : "Conor Driscoll - JS Dev";
  },
});

interface State {
  menuOpen: boolean;
  siteWidth: number | null;
}

const state: State = reactive({
  menuOpen: false,
  siteWidth: null,
});

const updateMenuBody = () => {
  // drawer
  if (state.menuOpen) {
    document.body.classList.add("overflow-hidden");
  } else {
    document.body.classList.remove("overflow-hidden");
  }
};

onMounted(() => {
  state.siteWidth = window.innerWidth;
  window.addEventListener("resize", () => {
    state.menuOpen = false;
    state.siteWidth = window.innerWidth;
  });
});

onUpdated(() => {
  updateMenuBody();
});

const ToggleMenu = () => {
  state.menuOpen = !state.menuOpen;
};
</script>

<template>
  <header>
    <div class="header">
      <NuxtLink to="/">
        <img src="./images/logo-dark.svg" width="60" height="60" />
      </NuxtLink>
      <a class="toggle" @click.prevent="ToggleMenu">
        <MenuEx :open="state.menuOpen" />
      </a>
    </div>
  </header>
  <NuxtPage />
  <Footer />
  <Overlay :open="state.menuOpen" />
</template>

<style scoped lang="scss">
.header {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    max-width: var(--site-container-width);
    margin: 10px auto;
}




</style>
