<template>
    <section id="video-showcase" class="video-demo-section">
        <div class="container">
            <h2>See <span class="highlight-primary">OmniHuman 1.5</span> in Action</h2>
            <p class="subtitle">This demo highlights how our advanced AI transforms a single image and voice input into a fully expressive digital human, showcasing the platform's capabilities in generating lifelike animations with emotional depth.</p>
            <div class="video-container">
                <video 
                    controls 
                    preload="none"
                    poster="https://resp.museohuman2.com/ohuman/image/omniHuman-15.webp"
                >
                    <source src="https://resp.museohuman2.com/ohuman/video/omniHuman-15.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                </video>
            </div>
            <p>Witness how <span class="highlight-primary">OmniHuman 1.5</span> transforms static images and audio into dynamic, lifelike character performances. This video showcases the power of <span class="highlight-primary">OmniHuman 1.5</span>'s cutting-edge AI for various content creation needs.</p>
        </div>
    </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
/* Video Demo Section */
.video-demo-section {
    background-color: #0d0d0d;
    padding: 80px 0;
    text-align: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.video-demo-section h2 {
    margin-bottom: 40px;
    color: #ffffff;
}

.video-container {
    position: relative;
    padding-bottom: 56.25%;
    /* 16:9 Aspect Ratio */
    height: 0;
    overflow: hidden;
    max-width: 900px;
    margin: 0 auto 30px auto;
    background-color: #000;
    /* Fallback for video area */
    border-radius: 10px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.video-container iframe,
.video-container video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
}
</style>
