<template>
<div class="main-container">
  <hero-component />
  <skills-showcase/>
  <div class="dashboard">
    <glass-panel @mark-active="markActive" :navItems="navItems" :active="active"></glass-panel>
    <glass-board>
      <Resume v-show="active === 0"></Resume>
      <Projects v-show="active === 1"></Projects>
    </glass-board>
  </div>
  <!-- <BackgroundElements></BackgroundElements> -->
</div>
</template>

<script>
import GlassBoard from './components/GlassBoard.vue';
import GlassPanel from './components/GlassPanel.vue';
// import BackgroundElements from './components/BackgroundElements.vue';
import Hero from './components/HeroComponent.vue'
import Resume from './components/Resume.vue'
import Projects from './components/ProjectComponents/Projects.vue'
import Skills from './components/Skills.vue'

export default {
  name: 'App',
  data() {
    return {
      navItems: ['Resume', 'Projects', 'test'],
      active: 1,
    }
  },
  components: {
    "glass-board": GlassBoard,
   // BackgroundElements,
    "glass-panel": GlassPanel,
    "hero-component": Hero,
    "skills-showcase": Skills,
    Resume,
    Projects,
  },
  methods: {
        markActive(idx) {
            console.log(idx);
            this.active = idx;
        },}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=JetBrains+Mono');

* {
  box-sizing: border-box;
  
}
body {
  background: #0F2027; 
  margin: 0;
}

.main-container {
  width: 100%;
  background: #0F2027;
}
#app {

  font-family: 'Outfit', monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #0F2027; 
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.dashboard {
    background-image: url('./assets/layered-waves-haikei-top.svg');
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin-bottom: 3rem;
    padding-top: 12rem;
}
</style>
