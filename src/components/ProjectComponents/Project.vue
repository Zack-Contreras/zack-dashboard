<template>
<div @click="toggleOpen()" class="github-project">
    <div :class="{'show':activeProject}" class="p-name">{{project.name}}<i :class="activeProject ? 'fas fa-minus-circle' : 'fas fa-plus-circle'"></i></div>
    <div :class="{'show':activeProject}" class="p-description">{{project.description}}</div>
</div>
</template>

<script>
export default {
    name: 'Project',
    props: {
        project: Object
    },
    data() {
        return {
            active: false,
        }
    },
    methods: {
        toggleOpen() {
            this.active = !this.active;
        }
    },
    computed: {
        activeProject() {
            return this.active;
        }
    }
}
</script>
<style>
.github-project {
    width: 100%;
    text-align: start;
    border-radius: .25rem;
    margin: auto;
    margin-bottom: .5rem;
    padding: 1rem;
    cursor: pointer;
    background: rgba(255, 255, 255, 0.4);
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
.p-name {
    position: relative;
    font-size: 1.5rem;
    transition: all 0.4s linear;
}
.p-description {
    opacity: 0;
    max-height: 0;
    overflow-y: hidden;
    transition: all 0.4s ease;
}
.show {
    max-height: fit-content;
    opacity: 1;
}
.fas {
    float: right;
    transition: all 0.4s ease;
}
</style>