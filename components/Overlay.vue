<script setup lang="ts"></script>

<template>
  <div class="overlay__container">
    <div class="overlay">
      <Transition appear class="delay-025">
      <div class="col__1">
          <div class="overlay__menu">
            <Transition appear class="delay-05">
            <NuxtLink to="/work">Work</NuxtLink>
            </Transition>
            <Transition appear class="delay-075">
            <NuxtLink to="/cv">Resumé</NuxtLink>
            </Transition>
          </div>
      </div>
      </Transition>
      <div class="col__2">
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

a {
  font-size: 2rem;
  text-transform: uppercase; 
  font-family: 'Henderson Slab', serif;
  width: fit-content;
  &::before {
  content: '';
  background-color: var(--color-hot-butter);
  position: absolute;
  left: 0;
  bottom: 10px;
  width: 100%;
  height: 8px;
  z-index: -1;
  transition: all .3s ease-in-out;
}
&:hover::before {
  bottom: 30%;
  left: 20px;
  height: 30px;
}
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
  background-position: left top;
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
  justify-content: center;
  height: 100%;
  a {
    margin-bottom: 1rem;
  }
}

.v-enter-active {
  transition: opacity 0.5s ease, transform 0.5s ease;
}
.v-enter-from {
  opacity: 0;
  transform: translateY(100px);
}

.delay-05 {
  transition-delay: 0.5s;
}

.delay-075 {
  transition-delay: 0.75s;
}

.delay-10 {
  transition-delay: 1s;
}


.delay-125 {
  transition-delay: 1.25s;
}

.delay-15 {
  transition-delay: 1.5s;
}
</style>
