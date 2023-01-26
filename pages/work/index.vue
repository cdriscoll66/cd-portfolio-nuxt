<script setup lang="ts">
import portfolio from "@/content/portfolio.json";
</script>

<template>
  <main>
    <div class="portfolio">
      <div class="portfolio__scrollable">
        <div class="portfolio__content">
          <div class="portfolio__intro">
            <h1>Recent Projects</h1>
            <p>
              Thanks For taking alook at my work. I've been lucky enough to work some pretty great collaborators, and I'm always looking for new opportunities to work with new people. If you're interested in working together, please drop me a line!
            </p>
          </div>
          <div class="portfolio__work">
            <ul>
              <li v-for="(piece, key) in portfolio" :key="key">
                <NuxtLink :to="`/work/${piece.slug}`">{{
                  piece.name
                }}</NuxtLink>
                <p>{{ piece.description }}</p>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss">
main {
  background-image: url(@/assets/images/astrolabe-3.webp);
  background-repeat: no-repeat;
  background-color: #000;
  background-size: cover;
  background-position: top right;
  height: 100vh;
  display: flex;
}
.portfolio {
  margin: 180px 50px;
  height: calc(100vh - 105px);
  overflow-y: scroll;
  padding-bottom: 50px;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  &::-webkit-scrollbar {
    display: none;
  }
  @media screen and (min-width: 1300px) {
    margin: 180px auto;
  }
}
.portfolio__scrollable {
  display: flex;
  margin-bottom: 100px;
  flex-flow: column nowrap;
  width: 100%;
  max-width: var(--site-content-width);

  border-color: var(--color-old-lace);
  border-style: solid;
  background-color: rgba(12, 29, 50, 0.9); //trapped darkness
  background-color: rgba(255, 245, 227, 0.9); //old lace
  /* border-image: url(@/assets/images/dashed-border.svg); */

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

  color: var(--color-maniac-mansion);
}

.portfolio__content {
  padding: 15px 50px 50px;
}

.portfolio__work {
  ul {
    list-style: none;
    padding: 0;

    li {
      padding: 1.5rem 0 .5rem;
      display: flex;
      flex-flow: row wrap;
      align-items: center;
      a {
        font-size: 1.8rem;
        font-weight: 700;
        margin-right: 30px;
      }
      p {
        font-size: 1.2rem;
        font-style: italic;
        margin-top: 0;
      
      }
    }
  }
}
</style>
