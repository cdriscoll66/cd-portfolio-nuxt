<script setup lang="ts">

const props = defineProps({
  pic: {
    type: String,
    required: false,
  },
});

</script>

<template>
    <div class="bg-img inner-shadow">
      <img :src="props.pic"/>
    </div>
</template>

<style scoped lang="scss">
.bg-img {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  top: 0;
  left: 0;
  flex: 0 1 50%;
  @media screen and (min-width: 1200px) {
    position: fixed;
    width: 100vw;
    height: 100vh;
  }
  img {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }
}

.inner-shadow:after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  box-shadow: inset 0 0em 4em rgb(0 0 0 / 33%);
}
</style>