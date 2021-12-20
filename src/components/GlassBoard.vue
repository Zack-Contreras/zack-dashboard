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
        background: linear-gradient(to right bottom, rgba(255, 255, 255, 0.4), rgba(255,255,255,0.3));
        width: 65vw;
        border-radius: .5rem;
        z-index: 2;
        backdrop-filter: blur(2rem);
        box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }
</style>