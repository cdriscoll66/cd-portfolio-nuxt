<script setup lang="ts">


const props = defineProps({
  open: {
    type: Boolean,
    required: true,
  },
  width: {
    type: Number,
    required: false,
  },
  look: {
    type: String,
    required: false,
  },
});

const screenWidth = computed(() => {
  let wdt = props.width ? props.width : 0;
  return wdt
});



</script>

<template>

<div class="branding">

  <div class="simple-brand">
        <NuxtLink to="/">
          <img v-if="props.look === 'bright'" src="@/assets/images/driscoll.svg" width="60" height="60" />
        <img v-else src="@/assets/images/cd-duotone.svg" width="60" height="60" />
      </NuxtLink>
    </div>

    
  <Transition>
  <div v-if="props.open && screenWidth > 500" class="brand-box">
    <div class="logo-box">
      <img src="@/assets/images/cd-duotone.svg" width="60" height="60" />
    </div>
    <div class="name-box">
      <p class="saltlname">
        <span class="c-salt">C</span><span class="saltline">ono</span
        ><span class="r-salt">r</span> <span class="d-salt">D</span
        ><span class="saltline">r</span><span class="i-salt">Í</span
        ><span class="saltline">scol</span><span class="l-salt">l</span>
      </p>
    </div>
    <div class="tag-box">
      <span>Front End Developer, Technologist</span>
    </div>
  </div>
</Transition>
    </div>
</template>

<style scoped lang="scss">

.branding {
    height: 100px;
}
.simple-brand {
    position: absolute;
    top: 21px;
    left: 20px;
    display: inline-block;
    vertical-align: bottom;
}
.brand-box {
  background-color: var(--color-white);
  border: 1px solid var(--color-black);
  display: grid;
  grid-template-columns: 100px 268px;
  grid-template-rows: 50px 50px;

  & > * {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}

.logo-box {
  grid-column: 1 / 1;
  grid-row: 1 / 3;
  a {
    height: 60px;
  }
  border-right: 1px solid var(--color-black);
}

.tag-box,
.name-box {
  color: var(--color-black);
  font-weight: 700;
  p {
    margin: 0;
    font-size: 16px;
    font-weight: bold;
  }
}
.name-box {
  grid-column: 2 / 2;
  grid-row: 1 / 1;
  border-bottom: 1px solid var(--color-black);
}

.tag-box {
  grid-column: 2 / 2;
  grid-row: 2 / 2;
  font-family: 'Henderson Slab', serif;
  font-size: 8pt;
}

p.saltname {
  font-feature-settings: "salt";
  text-transform: uppercase;
  font-weight: bold;
  font-size: 30px;
  letter-spacing: 8px;
}

span.saltline {
  font-weight: 700;
  text-transform: uppercase;
}

span.c-salt {
  font-feature-settings: "salt";
  font-size: 24px;
  letter-spacing: 8px;
  font-weight: 700;
}

span.d-salt {
  font-size: 24px;
  font-weight: 700;
}

span.i-salt {
  content: "\00cd";
  font-weight: 700;
  text-transform: uppercase;
}

span.l-salt {
  font-feature-settings: "salt" 6;
  text-transform: uppercase;
  font-weight: 700;
}

span.r-salt {
  font-feature-settings: "salt" 3;
  text-transform: uppercase;
  letter-spacing: 8px;
  font-weight: 700;
}

.v-enter-active {
  transition: opacity 0.75s ease;
  transition-delay: 0.5s;
}
.v-leave-active {
  transition: opacity 0.5s ease;
}
.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
