<template>
    <div>
        <iframe id="resume" class="embedded-resume" src="https://docs.google.com/document/d/e/2PACX-1vRrdydnGxRB28zI56czT9amjK3m5H5Qs6L7tPXSOVKLqhl6GlKeAVRtWQtGpVfwFTQRniMfCEwOeYtn/pub?embedded=true"></iframe>
    </div>
</template>
<script>
export default {
    name: 'Resume',
}
</script>

<style scoped>
div {
    height: 100%;
}
 .embedded-resume {
     height: 100%;
     width: 100%;
     padding: 1rem;
     border: none;
     border-radius: 2rem;
 }

 .embedded-resume div {
     margin: auto;
 }
</style>