<script setup lang="ts">
const props = defineProps({
    to:{
        type: String,
        required: true,
    },
    blank: {
type: Boolean,
required: false,
},
    text: {
        type: String,
        required: false,
    },
});
</script>

<template>
    <NuxtLink :to="props.to" class="dashed-button-link" :aria-label="props.text" target="props.blank" >
        {{ props.text }}
    </NuxtLink>
</template>

<style scoped lang="scss">
a {
  text-align: center;
  padding: 10px 20px;
  background-color: var(--color-glowing-lantern);
  color: var(--color-white);
  font-style: italic;
  margin: 0 20px 0 auto;
  line-height: 1;
  margin-top: 5px;
  border-color: var(--color-maniac-mansion);
  background-image: linear-gradient(
      to right,
      var(--color-maniac-mansion) 50%,
      transparent 50%
    ),
    linear-gradient(to left, var(--color-maniac-mansion) 50%, transparent 50%),
    linear-gradient(to bottom, var(--color-maniac-mansion) 50%, transparent 50%),
    linear-gradient(to top, var(--color-maniac-mansion) 50%, transparent 50%);
  background-position: left top, left bottom, left top, right top;
  background-repeat: repeat-x, repeat-x, repeat-y, repeat-y;
  background-size: 40px 2px, 40px 2px, 2px 30px, 2px 30px;
  transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  &:after {
    content: "";
    display: block;
    background-image: url(@/assets/images/arrow.svg);
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;
    height: 30px;
    width: 16px;
    margin-left: 10px;
  }
  &:before {
    content: "";
    height: 30px;
    width: 12px;
    position: absolute;
    right: 16px;
    background-color: var(--color-maniac-mansion);
    transition: background-color 0.3s ease-in-out;
  }
  &:hover {
    background-color: transparent;
    color: var(--color-maniac-mansion);
    &:before {
      background-color: var(--color-glowing-lantern);
    }
  }
  .dark & {
    &:after {
      background-image: url(@/assets/images/arrow-light.svg);
    }
    &:hover {
      color: var(--color-old-lace);
      &:before {
        background-color: var(--color-old-lace);
      }
    }
  }
}
</style>
