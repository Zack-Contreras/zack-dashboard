<template>
            <iframe id="resume" class="embedded-resume" src="https://docs.google.com/document/d/e/2PACX-1vRrdydnGxRB28zI56czT9amjK3m5H5Qs6L7tPXSOVKLqhl6GlKeAVRtWQtGpVfwFTQRniMfCEwOeYtn/pub?embedded=true"></iframe>
</template>
<script>
export default {
    name: 'Resume',
    mounted() {
    //     let myiFrame = document.getElementById("resume");
    //     let doc = myiFrame.contentDocument;
    //    console.log(doc.body.innerHTML)
    }
}
</script>

<style scoped>
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