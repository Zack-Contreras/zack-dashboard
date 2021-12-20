<template>

    <div class="glasspanel">
        <p @click="$emit('mark-active',index)" v-for="(nav, index) in navItems" :key="index" :class="{'active': active === index }">
            {{nav}}
        </p>
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
        height: auto;
        display: flex;
        background: linear-gradient(to right bottom, rgba(255, 255, 255, 0.5), rgba(255,255,255,0.3));
        box-shadow: rgba(0, 0, 0, 0.3) 0px 6px 18px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
        width: 65vw;
        margin: auto;
        border-radius: .5rem;
        z-index: 2;
        backdrop-filter: blur(2rem);
        margin-bottom: 1rem;
    }
    .avatar-img {
        height: 7rem;
        margin-bottom: 2rem;
    }
    p {
        border-radius: .25rem;
        margin: auto;
        width: 90%;
        padding: 1rem 1rem;
        cursor: pointer;
        transition: background-color 0.2s ease-in;
    }
    p.active {
        background: rgba(255, 255, 255, 0.4);
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
                font-weight: bold;
    }

    @media screen and (max-width: 672px) {
        .glasspanel {
            width: 85vw;
        }
    }
</style>