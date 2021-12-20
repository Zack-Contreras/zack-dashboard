<template>
  <div class="hero">
      <!-- <div class="hero-image"></div> -->
      <div class="outer-circle">
        <div class="inner-circle">  
        </div>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
      <div class="hero-title" :class="{animated: isLoaded}">
          <h1>Zackary Contreras</h1>
          <h2>Front-End Engineer | Web Developer</h2>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLoaded: false
    }
  },
  created() {
    setTimeout(() => {
        this.isLoaded = true;
    }, 100);
  }
}
</script>

<style>
    .hero {
        height: 113vh;
        width: 100%;
         background-image: url('../assets/layered-waves-haikei-bottom.svg');
         background-repeat: repeat-x;
         background-size: cover;
         display: flex;
         flex-direction: column-reverse;
        padding-bottom: 20rem;
        justify-content: center;
        align-items: center;
        color: white;
        animation: animatedBackground 20s ease-in-out infinite alternate;
    }

    @keyframes animatedBackground {
      from {
        background-position-x: 0;
      }
      to {
        background-position-x: 100%;
      }
    }

    .hero-title {
        width: 100%;
        margin: 0;
        padding-left: 2rem;
        text-align: left;
        transform: translateX(1000%);
        /*transition: 1s cubic-bezier(0.19,-0.2, 0.01, 1.43);*/
    }

    .hero-title > h1 {
      font-family: 'Comfortaa', cursive;
      font-size: 6rem;
      margin: 0;
      opacity: .9;
    }

    .hero-title > h2 {
      opacity: .7;
    }

    .hero-title.animated {
      transform: translateX(0);
    }

.outer-circle {
  display: none;
  position: absolute;
    right: 16%;
    transform: scale(1.5);
  height: 200px;
  width: 200px;
  background: linear-gradient(#0F2027, #3F5C74, #C98723);
  border-radius: 50%;
  animation: rotate 2.5s linear infinite;
  transition: .5s ease-in;
}

.outer-circle:hover {
  opacity: .5;
}

.outer-circle span {
  left: 0;
  position: absolute;
  height: 200px;
  width: 200px;
  background: linear-gradient(#C98723,#3F5C74,#0F2027 );
  border-radius: 50%;
}

span:nth-child(1) {
  filter: blur(5px);
}

span:nth-child(2) {
  filter: blur(10px);
}

span:nth-child(3) {
  filter: blur(25px);
}

span:nth-child(4) {
  filter: blur(150px);
}

.inner-circle {
  height: 180px;
  width: 180px;
  position: absolute;
  top: 10px;
  left: 10px;
  border-radius: 50%;
  z-index: 9;
}

@keyframes rotate {
  0% {
    filter: hue-rotate(0deg);
  }
  100% {
    filter: hue-rotate(360deg);
  }
}

@media screen and (min-width: 1670px) {
  .hero {
    height: 128vh;
  }
}
</style>