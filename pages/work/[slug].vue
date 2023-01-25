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
};




</script>

<template>
  <main>
    <div class="bg-img">
        <img v-bind:src="`/assets/images/tamu.webp`" />
    </div>
    <div class="description__container">
        <div class="description__top">
            <h1 class="h4">{{ single.name }}</h1>
                    <div class="description__links">
          <a
            v-for="(link, key) in single.links"
            :key="key"
            :href="link.url"
            target="_blank"
            >{{ link.text }}</a
          >
          </div>
        </div>
      
      <p>{{ single.full_description }}</p>
      <div class="description__bottom">

          <div class="description__collaborators">
            <div v-for="(collaborator, key) in single.collaborators" :key="key">
                <h5>{{ collaborator.role }}</h5>
                <h6>{{ collaborator.name }}</h6>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss">
main {
  width: 100%;
  max-width: var(--site-content-width);
  margin: 0 auto;
  padding-top: 150px;
  height: 100vh;
}

.bg-img {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
}

.description__container {
  color: var(--color-maniac-mansion);
  padding: 20px;
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
  width: 100%;
  max-width: 50%;
  position: absolute;
  bottom: 40px;
}

.description__top {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
}
.description__bottom {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
}

.description__collaborators {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    margin-top: 30px;
    width: 100%;
    & > div {
     width: 25%;
    }
}
</style>
