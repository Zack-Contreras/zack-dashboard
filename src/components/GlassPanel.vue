<template>
<div>
    <div class="glasspanel">
        <img class="avatar-img" src="@/assets/avatar-svgrepo-com.svg" alt="avatar icon">
        <p @click="$emit('mark-active',index)" v-for="(nav, index) in navItems" :key="index" :class="{'active': active === index }">
            {{nav}}
        </p>
    </div>
</div>
</template>

<script>
export default {
    name: "GlassPanel",
    props: {
        navItems: Array,
        active: Number,
    },
}
</script>

<style scoped>

    .glasspanel {
        background: white;
        height: 80vh;
        background: linear-gradient(to right bottom, rgba(255, 255, 255, 0.7), rgba(255,255,255,0.3));
        width: 15vw;
        border-radius: 2rem;
        z-index: 2;
        backdrop-filter: blur(2rem);
        margin-right: 1rem;
        padding-top: 50px;
    }
    .avatar-img {
        height: 7rem;
        margin-bottom: 2rem;
    }
    p {
        border-radius: 1rem;
        margin: auto;
        width: 90%;
        padding: 1rem 1rem;
        cursor: pointer;
        transition: background-color 0.2s ease-in;
    }
    p.active {
        background: rgba(255, 255, 255, 0.4);
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }
</style>