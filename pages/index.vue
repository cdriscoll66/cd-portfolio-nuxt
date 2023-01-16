<script setup lang="ts"></script>

<template>
  <TheSea />

  <main class="main">
    <section>
      <div class="intro">
        <h1>Hi, I&apos;m Conor.</h1>
        <h4 class="golden">
          I love making beautiful, performant, interesting things.
        </h4>
        <p>
          I&apos;m a freelance web developer, and technologist. I spend my days in Richmond, Virginia. Thanks for taking a look. 
        </p>
      </div>
    </section>
  </main>
</template>

<style scoped lang="scss">
.main {
  overflow: hidden;
  position: static;
}

.moon {
  position: absolute;
  bottom: 60vh;
  right: 55vh;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  z-index: 0;
  background-color: var(--color-glowing-lantern);
  box-shadow: 0px 0px 70px 30px rgba(245, 178, 62, 0.6);
}

.intro {
  margin-right: 20px;
   @media screen and (min-width: 400px) {
    margin-right: 50px;
  }
  @media screen and (min-width: 860px) {
    margin-right: 0;
    width: 80%;
  }

  @media screen and (min-width: 1120px) {
    margin-right: 0;
    width: 50%;
  }
}

.intro h1 {
  margin: 40px 0;
}

.intro p {
  line-height: 1.6;
}


</style>
