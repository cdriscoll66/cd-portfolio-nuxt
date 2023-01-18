<script setup lang="ts">
const router = useRouter();
const route = useRoute();

router.afterEach((to, from, next) => {
  state.menuOpen = false;
  next;
});

const headerLook = computed(() => {
  if (route.path === "/work") {
    return "bright";
  } else {
    return "";
  }
});

useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk
      ? `${titleChunk} - Conor Driscoll - JS Dev`
      : "Conor Driscoll - JS Dev";
  },
  htmlAttrs: {
    lang: "en",
  },
  meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'Richmond Based Front End Developer, Technologist - Conor Driscoll'
      }
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }]
});

interface State {
  menuOpen: boolean;
  siteWidth: number | undefined;
}

const state: State = reactive({
  menuOpen: false,
  siteWidth: 0,
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
      <Branding
        :open="state.menuOpen"
        :width="state.siteWidth"
        :look="headerLook"
      />

      <button class="toggle" @click.prevent="ToggleMenu" aria-label="menu toggle">
        <MenuEx :open="state.menuOpen" />
      </button>
    </div>
  </header>

  <NuxtPage />
  <Footer />
  <Transition>
    <Overlay v-if="state.menuOpen" />
  </Transition>
</template>

<style scoped lang="scss">
.header {
  position: fixed;
  left: 0;
  right: 0;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  max-width: var(--site-content-width);
  margin: 5px;
  z-index: 100;
  @media screen and (min-width: 1200px) {
    margin: 5px auto;
  }
}

.toggle {
  display: inline-block;
  line-height: 1;
  margin-right: 20px;
  background: none;
  border: none;
  outline: none;
  svg {
    vertical-align: bottom;
  }
}
.main {
  display: flex;
  flex-flow: column nowrap;
  min-height: 100vh;
}

.main > section {
  max-width: var(--site-content-width);
  margin: 0 auto;
  width: 100%;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}
.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.overflow-hidden {
  overflow: hidden;
}
</style>
