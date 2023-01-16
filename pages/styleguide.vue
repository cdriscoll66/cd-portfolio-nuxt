<script setup lang="ts">
useHead({
  title: "Styleguide",
});

const colors = [ 'glowing-lantern', 'hot-butter', 'sailor-boy', 'maniac-mansion', 'trapped-darkness', 'mercury', 'old-lace',   'black' , 'light-gray','medium-gray', 'dark-gray','white'];

const colorVar = (color: string) => {
    return `var(--color-${color})`
}

</script>

<template>
  <section class="container scrollable">
    <h1 class="headline">Wayfinder Ui Kit</h1>
    <p>-by Conor D.</p>
    <hr />
    <div class="container">
      <div class="colorswatches">
        <div v-for="color, id in colors" :key="id" class="colorswatch" :style="{backgroundColor: colorVar(color) }"><span>{{ color.replace('-', ' ') }}</span></div>
      </div>
    </div>
    <hr />
    <div class="container lightbg">
      <div class="colorswatches">
        <div v-for="color, id in colors" :key="id" class="colorswatch" :style="{backgroundColor: colorVar(color) }"><span>{{ color.replace('-', ' ') }}</span></div>
      </div>
    </div>
    <div class="container">
      <h2>Type</h2>
      <h1 class="golden">Heading 1</h1>
      <h2>Heading 2</h2>
      <h3>Heading 3</h3>
      <h4>Heading 4</h4>
      <h5>Heading 5</h5>
      <h6>Heading 6</h6>
      <p class="lede">
        Lede Paragraph - Eos nobis delectus ex. Aut minima incidunt maxime
        sapiente quaerat ratione hic nulla. Delectus sequi eligendi consectetur.
        Debitis ut reiciendis doloremque.
      </p>
      <p>
        Eos nobis delectus ex. Aut minima incidunt maxime
        sapiente quaerat ratione hic nulla. Delectus sequi eligendi consectetur.
        Debitis ut reiciendis doloremque. Delectus sequi eligendi consectetur.
        Debitis ut reiciendis doloremque.
      </p>
      <p>
        Sit dolores doloremque eos. Aut amet voluptas est. Eligendi quod
        dignissimos ut in voluptatem. Quas deleniti qui est doloribus ducimus
        voluptas odit. Enim nesciunt exercitationem eveniet molestiae sint.
      </p>
      <p>
        Et neque a at. Eius error autem nemo excepturi consectetur accusamus.
        Consequatur deleniti quos rerum laboriosam esse rerum et. Qui
        reprehenderit possimus fuga provident iure ipsam. Nihil et animi tempore
        consequuntur placeat qui.
      </p>
    </div>
    <hr />
  </section>
</template>

<style scoped lang="scss">

.scrollable {
  overflow-y: scroll;
  height: 100vh;
  padding-bottom: 100px;
}
h1.headline {
  margin-bottom: 10px;
}

.colorswatches {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  margin-bottom: 20px;
  gap: 20px;
  padding: 15px;
}

.lightbg {
  background-color: var(--color-old-lace);
}

.colorswatch {
  flex: 0 0 calc(25% - 15px);
  height: 100px;
  border: 1px solid var(--color-black);
}

.colorswatch span {
  font-size: .75rem;
  padding: 10px;
  text-transform: capitalize;
}
</style>
