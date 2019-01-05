<template>
<div class="videoWrapper">
    <!-- <div class="overlay" /> -->
    <video autoplay loop muted playsinline>
        <source src="../assets/heroVideo.mp4" type="video/mp4"> Your browser doesn't support video tag. I suggest you upgrade your browser.
    </video>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.videoWrapper {
    .overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 1;
        background-color: rgba(0,0,0,.4);

    }

    video {
        position: fixed;
        right: 0;
        top: 0;
        min-width: 100%;
        min-height: 100%;
    }
}
</style>
