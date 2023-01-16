<script setup lang="ts"></script>

<template>
  <main>
    <div class="portfolio">
      <div class="portfolio__scrollable">
        <div class="portfolio__content">
          <div class="portfolio__intro">
            <h1>Recent Projects</h1>
            <p>
              Lorem Ipsum Here is some of my recent work - explainers, credits
              and images are comgin soon.
            </p>
          </div>
          <div class="portfolio__work">
            <ul>
              <li>
                <NuxtLink to="https://start.k8ssandra.io" target="_blank"
                  >K8ssandra Configuration Builder</NuxtLink
                >
                <span>A configurator for lorem ipsum</span>
              </li>
              <li>
                <NuxtLink to="https://start.k8ssandra.io" target="_blank"
                  >Hot97.com</NuxtLink
                >
                <span>New York's number one hip hop station</span>
              </li>
              <li>
                <NuxtLink
                  to="https://luck-100-years.netlify.app/"
                  target="_blank"
                  >Luck 100 years celebration</NuxtLink
                >
                <span
                  >Luck Companies is celebrating a centennial - and wanted to
                  commemorrate their history with a showcase</span
                >
              </li>
              <li>
                <NuxtLink to="https://www.architect.io/" target="_blank"
                  >Architect.io</NuxtLink
                >
                <span
                  >Landing and marketing pages for Architect.io and it's
                  application</span
                >
              </li>
              <li>
                <NuxtLink to="https://www.teamcolab.com" target="_blank"
                  >Team Colab</NuxtLink
                >
                <span
                  >I worked as a Senior Dev for team colab for years, and built the companies site.</span
                >
              </li>
              <li>
                <NuxtLink to="https://grad.tamu.edu/" target="_blank"
                  >Texas A & M Graduate School Portal</NuxtLink
                >
                <span
                  >Front End Dev for Exterior teams for Kentico, Strategy and
                  Design</span
                >
              </li>
              <li>
                <NuxtLink
                  to="https://nclottery-pick4.netlify.app/"
                  target="_blank"
                  >North Carolina Pick 4</NuxtLink
                >
                <NuxtLink
                  to="https://nclottery-pick3.netlify.app/"
                  target="_blank"
                  >& Pick 3</NuxtLink
                >
                <span
                  >Game Design and Build for Educating players on Game
                  approach</span
                >
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
  background-image: url(@/assets/images/astrolabe-2.jpg);
  background-repeat: no-repeat;
  background-color: #000;
  background-size: cover;
  background-position: top right;
  height: 100vh;
  display: flex;
}
.portfolio {
  margin: 105px 50px;
  height: calc(100vh - 105px);
  overflow-y: scroll;
  padding-bottom: 50px;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
  &::-webkit-scrollbar {
    display: none;
  }
}
.portfolio__scrollable {
  display: flex;
  flex-flow: column nowrap;
  width: 100%;
  max-width: var(--site-container-width);

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
  @media screen and (min-width: 1540px) {
    margin: 105px auto;
  }
}

.portfolio__content {
  padding: 15px 50px;
}

.portfolio__work {
  ul {
    list-style: none;
    padding: 0;

    li {
      padding: 0.5rem 0;
      display: flex;
      flex-flow: row wrap;
      align-items: center;
      a {
        font-size: 1.6rem;
        font-weight: 700;
        margin-right: 30px;
      }
      span {
        font-size: 1.3rem;
        font-style: italic;
      }
    }
  }
}
</style>
