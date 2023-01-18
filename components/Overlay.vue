<script setup lang="ts"></script>

<template>
  <div class="overlay__container">
    <div class="overlay">
      <div class="col__1">
        <Transition appear class="delay-075">
          <div class="overlay__statement">
            <h3>
              This is the overlay Statement. I need to write soemthing worth
              reading here.
            </h3>
          </div>
        </Transition>
        <Transition appear class="delay-125">
          <div class="overlay__menu">
            <NuxtLink to="/work">Work</NuxtLink>
            <NuxtLink to="/styleguide">About</NuxtLink>
          </div>
        </Transition>
      </div>
      <div class="col__2">
        <div class="overlay__form">
          <h3>Form</h3>
          <EmailForm />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.overlay__container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: var(--color-old-lace);
  color: var(--color-maniac-mansion);
  z-index: 2;
  display: flex;
  justify-content: center;
}

h3 {
  font-size: 3rem;
  margin-top: 0;
  line-height: 1.1;
}
.overlay {
  margin: 135px 5px 20px;
  /* background-color: var(--color-sailor-boy); */
  width: 100%;
  max-width: var(--site-content-width);
  display: flex;
  @media screen and (min-width: 1210px) {
    margin: 135px auto 5px;
  }
}

.col__1 {
  padding: 0 30px;
  margin: 40px 0;
  flex: 1 0 45%;
  background-image: linear-gradient(to bottom,var(--color-trapped-darkness) 50%,transparent 50%);
  background-position: right top;
  background-repeat: repeat-y;
  background-size: 2px 50px;
}

.col__2 {
  padding: 0 30px;
  margin: 40px 0;
  flex: 1 0 55%;
}

.overlay__menu {
  display: flex;
  flex-flow: column nowrap;
  a {
    padding-top: 1rem;
  }
}

.v-enter-active {
  transition: opacity 0.5s ease, transform 0.5s ease;
}
.v-enter-from {
  opacity: 0;
  transform: translateY(20%);
}

.delay-075 {
  transition-delay: 0.75s;
}

.delay-125 {
  transition-delay: 1.25s;
}
</style>
