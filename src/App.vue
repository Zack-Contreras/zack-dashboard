<template>
<div>
  <div class="dashboard">
  <glass-panel @mark-active="markActive" :navItems="navItems" :active="active"></glass-panel>
  <glass-board>
    <Resume v-show="active === 0"></Resume>
    <Projects v-show="active === 1"></Projects>
  </glass-board>
  </div>
  <BackgroundElements></BackgroundElements>
</div>
</template>

<script>
import GlassBoard from './components/GlassBoard.vue';
import GlassPanel from './components/GlassPanel.vue';
import BackgroundElements from './components/BackgroundElements.vue';
import Resume from './components/Resume.vue'
import Projects from './components/Projects.vue'

export default {
  name: 'App',
  data() {
    return {
      navItems: ['Resume', 'Projects', 'test'],
      active: 0,
    }
  },
  components: {
    "glass-board": GlassBoard,
    BackgroundElements,
    "glass-panel": GlassPanel,
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
background: #0F2027;  /* fallback for old browsers */
background: -webkit-linear-gradient(to top left, #2C5364, #203A43, #0F2027);  /* Chrome 10-25, Safari 5.1-6 */
background: linear-gradient(to top left, #2C5364, #203A43, #0F2027); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */


overflow-y: hidden;
}
#app {
  overflow-y: hidden;

  font-family: 'JetBrains Mono', monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.dashboard {
  display: flex;
}
</style>
