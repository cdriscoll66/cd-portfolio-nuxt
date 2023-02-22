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
          </div>
          <div class="portfolio__work">
            <ul>
              <li v-for="(piece, key) in portfolio.recent" :key="key">
                <NuxtLink :to="`/work/${piece.slug}`">{{
                  piece.name
                }}</NuxtLink>
                <p>{{ piece.description }}</p>
              </li>
            </ul>
          </div>
            <h4 class="comingsoon">More to come...</h4>
            <div class="portfolio__intro">
            <h3>Maintenance</h3>
            <p>Often, I've been tasked with on stepping in to improve or maintain sites and systems built by others. These come with a unique set of challenges, both difficult and interesting. Here are a sample of those projects.</p>
          </div>
          <div class="portfolio__work">
            <ul>
              <li v-for="(piece, key) in portfolio.maintenance" :key="key">
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
  margin: 110px 10px;
  height: calc(100vh - 105px);
  overflow-y: scroll;
  padding-bottom: 50px;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  width: 100%;
  &::-webkit-scrollbar {
    display: none;
  }
}
.portfolio__scrollable {
  display: flex;
  margin: 0 10px 100px;
  flex-flow: column nowrap;
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
  @media screen and (min-width: 600px) {
    margin: 0 50px 100px;
  }
  @media screen and (min-width: 1300px) {
    margin: 0 auto 100px;
  }
}

.portfolio__content {
  padding: 15px 50px 50px;
}

.portfolio__work {
  width: 100%;
  ul {
    list-style: none;
    padding: 0;
  
    li {
      padding: 1.5rem 0 .5rem;
      display: flex;
      flex-flow: column nowrap;
      align-items: flex-start;
      max-width: var(--breakpoint-md);
      margin: 10px auto;
      border-bottom: 3px solid var(--color-hot-butter);

      a {
        font-size: 1.8rem;
        font-weight: 700;
        margin-right: 30px;
        line-height: 1;
        color: var(--color-maniac-mansion);
      }
      p {
        font-size: 1.2rem;
        line-height: 1;
        font-style: italic;
        margin-top: 10px;
        color: var(--color-medium-gray);
      
      }
    }
  }
}

.comingsoon {
  text-align: center;
  font-size: 1.2rem;
  font-style: italic;
  margin-top: 0;
  margin-bottom: 0;
  padding: 1.5rem 0 .5rem;
  color: var(--color-medium-gray);
}

.portfolio__intro {
  p {
    font-size: 1.2rem;
    line-height: 1;
    font-style: italic;
    margin-top: 10px;
    color: var(--color-medium-gray);
  }
}
</style>
