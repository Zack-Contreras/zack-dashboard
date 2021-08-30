<template>
<div>
    <div class="glassboard">
        <slot></slot>
    </div>
</div>
</template>

<script>
export default {
    name: "GlassBoard",
}
</script>

<style scoped>

    .glassboard {
        background: white;
        height: 80vh;
        background: linear-gradient(to right bottom, rgba(255, 255, 255, 0.7), rgba(255,255,255,0.3));
        width: 65vw;
        border-radius: 2rem;
        z-index: 2;
        backdrop-filter: blur(2rem);
    }
</style>