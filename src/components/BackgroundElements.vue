<template>
<div>
    <div class="circles circle-one"></div>
    <div class="circles circle-two"></div>
</div>
</template>

<script>
export default {
    name: "BackgroundElements",
}
</script>

<style scoped>

    .circles {
        background: white;
        background: linear-gradient(
            to right bottom,
            rgba(255, 255, 255, 0.8),
            rgba(255, 255, 255, 0.3)
        );
        height: 15rem;
        width: 15rem;
        position: absolute;
        border-radius: 20%;
        z-index: -1;
    }
    .circle-one {
        top: 5%;
        right: 15%;
    }
    .circle-two {
        bottom: 5%;
        left: 5%;
    }
</style>