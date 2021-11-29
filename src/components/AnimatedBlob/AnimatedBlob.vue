<template>
    <div class="animated-blob-container">
        <svg id="visual" viewBox="0 0 900 600" width="900" height="600" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
            <g transform="translate(441.67958971759094 273.5815388600114)"><path id="blob1" d="M130.7 -211C171.7 -202.6 208.8 -172.3 231.2 -133.5C253.6 -94.7 261.3 -47.3 236.6 -14.3C211.8 18.8 154.6 37.5 131.8 75.6C109 113.7 120.5 171.2 104.2 209.1C88 247.1 44 265.5 -0.4 266.3C-44.8 267 -89.7 250 -121.6 221.1C-153.5 192.1 -172.4 151.3 -186.5 112.5C-200.6 73.7 -209.8 36.8 -221.2 -6.6C-232.6 -50 -246.2 -100 -221 -119.6C-195.9 -139.3 -131.9 -128.5 -88.6 -135.5C-45.3 -142.5 -22.7 -167.3 11.1 -186.5C44.8 -205.7 89.7 -219.3 130.7 -211" :fill="getFill"></path></g>
            <g transform="translate(438.92194476216355 284.75502329083696)"><path style="visibility: hidden" id="blob2" d="M170.1 -182.9C211.6 -167.9 230.4 -105.9 239.1 -44C247.8 17.9 246.4 79.7 218.3 123.7C190.1 167.6 135.1 193.8 80.6 207.6C26.1 221.5 -27.8 223 -57.4 195.7C-87 168.5 -92.2 112.4 -122.7 67.1C-153.3 21.9 -209.1 -12.4 -219.7 -53.8C-230.4 -95.2 -195.9 -143.8 -151.7 -158.3C-107.6 -172.9 -53.8 -153.4 5.2 -159.7C64.3 -165.9 128.6 -197.9 170.1 -182.9" :fill="getFill"></path></g>
        </svg>
        <div class="blob-content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
import KUTE from 'kute.js'
export default {
    name: 'AnimatedBlob',
    props: {
        fill: {
            type: String,
            default: "#2C5162"
        }
    },
    computed: {
        getFill() {
            return this.fill;
        }
    },
    methods: {
    },
    mounted() {
        KUTE.fromTo(
            '#blob1',
            {path: '#blob1'},
            {path: '#blob2'},
            {repeat: 999, duration: 4000, yoyo: true}
        ).start();
    }
}
</script>

<style>
    .animated-blob-container {
        position: relative;
        max-height: 200px;
    }
    .blob-content {
        position: absolute;
        top: 25%;
        left: 0;
        right: 0;
    }
    svg {
        width: 100%;
        max-height: 600px;
        transform: translateY(-175px);
    }
</style>