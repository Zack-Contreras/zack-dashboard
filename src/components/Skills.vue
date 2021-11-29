<template>
    <div class="skill-showcase">
        <animated-blob fill="#c98723">
            <h2 class="skills-header">Experienced in</h2>
            <div class="skills">
                <div class="skill" :key='skill' v-for="skill in skills">
                    <i :class='getClassName(skill)'></i>
                </div>
            </div>
        </animated-blob>
    </div>
</template>

<script>
import AnimatedBlob from './AnimatedBlob/AnimatedBlob.vue'
export default {
    name: 'Skills',
    components: {
    "animated-blob": AnimatedBlob,
    },
    data() {
        return {
            skills: [
                'html5',
                'css3-alt',
                'js',
                'vuejs',
                'php'
            ]
        }
    },
    methods: {
        getClassName(skill) {
            return `fab fa-${skill}`
        }
    }
}
</script>

<style>
    .skill-showcase {
        margin: 0;
        background: #203A43;
        color: white;
        max-height: 250px;
    }

    .skills-header {
        margin-top: 0;
    }

    .skills {
        display: flex;
        max-width: 30%;
        margin: auto;
        justify-content: space-between;
    }

    .skill > .fab {
        font-size: 4rem;
    }
</style>