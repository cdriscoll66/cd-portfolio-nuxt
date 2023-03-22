<script setup lang="ts"></script>

<template>
  <TheSea />

  <main class="main">
    <section>
      <div class="intro">
        <h1>Hi, I&apos;m Conor.</h1>
        <h2 class="h4 golden">
          I love making beautiful, performant, interesting things.
        </h2>
        <p>
          I&apos;m a JavaScript enthusiast & technologist. I spend my days
          in Richmond, Virginia working with the very cool team at <a
            href='https://www.interactivestrategies.com/' target="_blank">Interactive Strategies.</a>
        </p>
      </div>
    </section>
  </main>
</template>

<style scoped lang="scss">
.main {
  overflow: hidden;
  position: static;
  display: flex;
  flex-flow: column nowrap;
  min-height: 100vh;
  padding-top: 105px;

  &>section {
    max-width: var(--site-content-width);
    margin: 0 30px;
    z-index: 1;

    @media (min-width: 1260px) {
      margin: 0 auto;
      width: 100%;
    }
  }
}

.intro {
  margin-right: 5px;
  margin-left: 5px;

  @media screen and (min-width: 400px) {
    margin-right: 50px;
  }

  @media screen and (min-width: 860px) {
    margin-right: 0;
    width: 75%;
  }

  @media screen and (min-width: 1120px) {
    width: 58%;
  }

  @media screen and (min-width: 1440px) {
    width: 50%;
  }
}

.intro h1 {
  margin: 40px 0;
}

.intro p {
  line-height: 1.6;

  a {
    color: var(--color-glowing-lantern);
    width: fit-content;

    &::before {
      content: "";
      background-color: var(--color-maniac-mansion);
      position: absolute;
      left: 0;
      bottom: 1px;
      width: 100%;
      height: 0px;
      z-index: -1;
      transition: all 0.3s ease-in-out;
    }

    &:hover::before {
      bottom: 10%;
      left: 5px;
      height: 20px;
    }
  }
}</style>
