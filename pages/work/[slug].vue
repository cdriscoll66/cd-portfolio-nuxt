<script setup lang="ts">
import portfolio from "~/content/portfolio.json";

const route = useRoute();

const single = portfolio.find((piece) => piece.slug === route.params.slug) ?? {
  name: undefined,
  description: undefined,
  slug: undefined,
  full_description: undefined,
  collaborators: [],
  links: [],
  media: [],
  dark: Boolean,
  right: Boolean,
};

useHead({
  title: single.name,
});
</script>

<template>
  <main>
    <div
      :class="[
        'description__container',
        single.dark ? 'dark' : '',
        single.right ? 'right' : '',
      ]"
    >
      <div class="description__top">
        <h1 class="h4 description__title">{{ single.name }}</h1>
        <div class="description__links">
          <DashedButtonLink v-for="(link, key) in single.links" :to="link.url" :key="key" :blank="true" :text=link.text />
        </div>
      </div>

      <p>{{ single.full_description }}</p>
      <div class="description__bottom">
        <div class="description__collaborators">
          <div v-for="(collaborator, key) in single.collaborators" :key="key">
            <h5>{{ collaborator.role }}</h5>
            <h6 v-for="name in collaborator.name">{{ name }}</h6>
          </div>
        </div>
      </div>
      <NuxtLink to="/work" class="back2work" aria-label="Back to work">
        &lt; Work </NuxtLink>
    </div>



    <BgImg :pic="`/images/${single.media[0].src}`" />
  </main>
</template>

<style scoped lang="scss">

main {
  width: 100%;
  max-width: var(--site-content-width);
  margin: 0 auto;
  height: 100vh;
  display: flex;
  flex-flow: column-reverse nowrap;
  @media screen and (min-width: 1200px) {
    padding-top: 150px;
  }
  p {
    font-size: 0.9rem;
    line-height: 1.2;
  }
}

.description__container {
  padding: 30px 20px 15px;
  z-index: 1;
  color: var(--color-maniac-mansion);
  border-color: var(--color-old-lace);
  border-style: solid;
  /* background-color: rgba(12, 29, 50, 0.9); //trapped darkness */
  background-color: rgba(255, 245, 227, 0.9); //old lace
  background-image: linear-gradient(
      to right,
      var(--color-trapped-darkness) 50%,
      transparent 50%
    ),
    linear-gradient(
      to right,
      var(--color-trapped-darkness) 50%,
      transparent 50%
    ),
    linear-gradient(
      to bottom,
      var(--color-trapped-darkness) 50%,
      transparent 50%
    ),
    linear-gradient(
      to bottom,
      var(--color-trapped-darkness) 50%,
      transparent 50%
    );
  background-position: left top, left bottom, left top, right top;
  background-repeat: repeat-x, repeat-x, repeat-y, repeat-y;
  background-size: 50px 2px, 50px 2px, 2px 50px, 2px 50px;
  position: relative;
  flex: 1 0 50%;
  max-height: 50%;
  overflow: scroll;
  @media screen and (min-width: 1200px) {
    overflow: unset;
    max-height: unset;
    position: absolute;
    max-width: 60%;
    margin: 0;
    bottom: 40px;
  }
}

.description__top {
  display: flex;
  flex-flow: column nowrap;
  align-items: flex-start;
  justify-content: space-between;
  @media screen and (min-width: 680px) {
    flex-flow: row nowrap;
    align-items: center;
    gap: 20px;
  }
}
.description__bottom {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-evenly;
}

.description__links {
  flex: 0 1 75%;
}
.description__links {
  display: flex;
  flex-flow: row nowrap;
  flex: 1 0 25%;
  @media screen and (min-width: 680px) {
    flex-flow: column nowrap;
    align-items: center;
  }
}
.description__collaborators {
  display: flex;
  flex-flow: row wrap;
  justify-content: flex-end;
  margin: 30px 0 10pxw;
  width: 100%;
  & > div {
    width: 25%;
    padding: 2px;
  }
  h6 {
    margin: 0;
    font-weight: 400;
    /* text-transform: uppercase;  */
    font-size: 0.6875rem;
    font-family: "Henderson Slab", serif;
  }
}

.back2work {
  font-family: "Henderson Slab", serif;
  font-size: 0.75rem;
  text-transform: uppercase;
  margin-top: 10px;
  font-weight: bold;
  opacity: .9;
  transition: opacity 0.2s ease-in-out;
  &:hover {
    opacity: 1;
  }
  .dark & {
    color: var(--color-glowing-lantern);
  }
} 
.dark {
  background-color: rgba(3,58,86, 0.9);
  color: var(--color-old-lace);
  border-color: var(--color-maniac-mansion);
  background-image: linear-gradient(
      to right,
      var(--color-old-lace) 50%,
      transparent 50%
    ),
    linear-gradient(to right, var(--color-old-lace) 50%, transparent 50%),
    linear-gradient(to bottom, var(--color-old-lace) 50%, transparent 50%),
    linear-gradient(to bottom, var(--color-old-lace) 50%, transparent 50%);
}

.right {
  right: 0;
}


</style>
