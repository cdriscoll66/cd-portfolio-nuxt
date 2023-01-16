<script setup lang="ts">

</script>

<template>

<div class="bgvideo">
    <video autoPlay muted loop>
        <source src="/media/lapping-waves.mp4" type="video/mp4" />
    </video>
</div>

</template>

<style scoped lang="scss">
.bgvideo {
    height: 280px;
    z-index: 0;
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: #081622;
}

.bgvideo > video {
    -moz-transform: scale(-1, 1); 
    -webkit-transform: scale(-1, 1); -o-transform: scale(-1, 1); 
    transform: scale(-1, 1); 
    filter: FlipH;
    -ms-filter: "FlipH";
    mask-image: linear-gradient(90deg, rgba(0,0,0,1) 0%, rgba(0,0,0,1) 85%, rgba(0,0,0,0) 100%);
    mask-mode: alpha;
    height: 100%;
    position: absolute;
    right: -545px;

    @media screen and (min-width: 860px) {
        right: calc(-1 * (1450px - 105vw));
    }

    @media screen and (min-width: 1250px) {
        right: -10vw;
    }

}
</style>