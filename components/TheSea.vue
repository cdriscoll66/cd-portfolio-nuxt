<script setup lang="ts">

</script>

<template>
    <div class="bg">
        <div class="moon"></div>
        <div class="star"></div>
        <div class="clouds"></div>
        <BgVideo />
    </div>
</template>

<style scoped lang="scss">

.bg {
    position: absolute;
    pointer-events: none;
    top: -1px;
    bottom: -1px;
    left: -1px;
    right: -1px;
    z-index: 1;
}

.bg:after {
  content: "";
  z-index: -1;
  position: absolute;
  width: 100vw;
  min-width: 1440px;
  height: 200%;
  --s1: radial-gradient(0.1vmin 0.1vmin at 50% 50%, #ffffff, #fff0);
  --s2: radial-gradient(0.2vmin 0.2vmin at 50% 50%, #ffffff, #fff0);
  background-image: var(--s1), var(--s1), var(--s1), var(--s2), var(--s2),
    var(--s1), var(--s2), var(--s1), var(--s2), var(--s1), var(--s2), var(--s1),
    var(--s2), var(--s1), var(--s1), var(--s2), var(--s2), var(--s1), var(--s1),
    var(--s2), var(--s1), var(--s1);
  background-repeat: repeat-x;
  background-size: 26% 25%, 43.33% 33.33%, 50% 80%, 20% 20%, 33.33% 75.33%,
    26% 73%, 39.33% 22%, 33.33% 26%, 31% 32%, 14.33% 35.33%, 18.33% 62.33%,
    39.33% 86.33%, 29.33% 69%, 12.33% 30.33%, 29.33% 41.33%, 22.33% 46.33%,
    35.33% 27.33%, 22.33% 39.33%, 20.33% 44.33%, 33.33% 56.33%;
  filter: drop-shadow(0px 0px 2px #fff) drop-shadow(0px 0px 5px #fff);
  background-position: -8% -10%;
  transform: translateZ(-100vmin);
  transition: all 3s var(--cbz) 0s;
  top: -16vmin;
}

.moon {
  position: absolute;
  bottom: 60vh;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  z-index: 0;
  background-color: var(--color-glowing-lantern);
  box-shadow: 0px 0px 70px 30px rgba(245, 178, 62, 0.6);

  right: -35px;

@media screen and (min-width: 860px) {
    right: calc(-1 * (938px - 105vw));
}

@media screen and (min-width: 1250px) {
    right: calc(512px + -10vw);
}
}
.clouds {
  position: absolute;
  top: 15vh;
  min-width: 1000px;
  width: 100vw;
  height: 100%;
  background: radial-gradient(ellipse at 10% 23%, #fff1 4vh, #fff0 15vh),
    radial-gradient(ellipse at 0% 15%, #fff1 4vh, #fff0 8vh),
    radial-gradient(circle at 6% 17%, #fff1 4vh, #fff0 8vh),
    radial-gradient(ellipse at 4% 16%, #fff1 1vh, #fff0 5vh),
    radial-gradient(circle at 9% 16%, #fff1 1vh, #fff0 5vh),
    radial-gradient(ellipse at 12% 18%, #fff1 1vh, #fff0 5vh),
    radial-gradient(circle at 17% 19%, #fff1 2vh, #fff0 6vh),
    radial-gradient(ellipse at 13% 13%, #fff1 1vh, #fff0 6vh),
    radial-gradient(ellipse at 22% 20%, #fff1 2vh, #fff0 8vh),
    radial-gradient(circle at 4% 22%, #fff1 0vh, #fff0 4vh),
    radial-gradient(circle at 7% 24%, #fff1 0vh, #fff0 4vh),
    radial-gradient(ellipse at 10% 22%, #fff1 0vh, #fff0 4vh),
    radial-gradient(circle at 30% 19%, #fff2 0vh, #fff0 13vh),
    radial-gradient(circle at 26% 13%, #fff1 0vh, #fff0 4vh),
    radial-gradient(circle at 33% 15%, #fff1 -3vh, #fff0 7vh),
    radial-gradient(circle at 45% 19%, #fff1 4vh, #fff0 14vh),
    radial-gradient(circle at 38% 20%, #fff1 -3vh, #fff0 7vh),
    radial-gradient(circle at 52% 20%, #fff1 0vh, #fff0 6vh),
    radial-gradient(circle at 56% 15%, #fff1 0vh, #fff0 7vh),
    radial-gradient(circle at 58% 18%, #fff1 0vh, #fff0 7vh),
    radial-gradient(circle at 41% 26%, #fff1 2vh, #fff0 8vh),
    radial-gradient(circle at 60% 15%, #fff1 0vh, #fff0 7vh),
    radial-gradient(circle at 63% 12%, #fff1 0vh, #fff0 7vh),
    radial-gradient(circle at 63% 21%, #fff1 4vh, #fff0 15vh),
    radial-gradient(circle at 60% 25%, #fff1 2vh, #fff0 7vh),
    radial-gradient(ellipse at 63% 20%, #fff1 0vh, #fff0 7vh),
    radial-gradient(circle at 71% 25%, #fff1 2vh, #fff0 9vh),
    radial-gradient(ellipse at 84% 22%, #fff1 -1vh, #fff0 8vh),
    radial-gradient(ellipse at 78% 25%, #fff1 -1vh, #fff0 10vh),
    radial-gradient(ellipse at 90% 18%, #fff1 -1vh, #fff0 10vh),
    radial-gradient(ellipse at 93% 17%, #fff1 2vh, #fff0 11vh),
    radial-gradient(circle at 79% 17%, #fff1 -3vh, #fff0 7vh),
    radial-gradient(ellipse at 73% 12%, #fff1 -3vh, #fff0 6vh),
    radial-gradient(ellipse at 68% 15%, #fff1 -2vh, #fff0 9vh),
    radial-gradient(ellipse at 95% 25%, #fff1 -2vh, #fff0 9vh),
    radial-gradient(ellipse at 98% 26%, #fff1 -2vh, #fff0 9vh),
    radial-gradient(ellipse at 90% 23%, #fff1 -2vh, #fff0 9vh);
  transform: translateZ(-100vh);
  transition: all .3s linear 0s;
  opacity: 0.6;
}
</style>