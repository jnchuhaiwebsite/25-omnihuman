<template>
    <header class="hero-section">
        <div class="container hero-layout">
            <div class="hero-text">
                <h1><span class="highlight-primary">OmniHuman 1.5</span> - The New Standard for <span
                        class="highlight-secondary">AI-Powered Virtual Human</span> Content Generation</h1>
                <p>Welcome to <span class="highlight-primary">OmniHuman 1.5</span>, an advanced AI-powered character
                    animation platform. It excels by generating expressive
                    digital avatars from just a single image and a voice input. Our innovative
                    system integrates Multimodal Large Language Models
                    with Diffusion Transformers, simulating both intuitive reactions and deliberate reasoning. This empowers
                    the platform to produce animations with unparalleled emotional
                    depth, semantic coherence, and natural motion.</p>
                <!-- <a href="#demo" class="btn btn-primary">Experience OmniHuman 1.5 Now</a> -->
            </div>
            <div class="hero-video">
                <div class="video-container">
                    <video 
                        ref="videoPlayer"
                        preload="none"
                        poster="https://resp.musesteamer2.com/steamer/images/omniHuman-15.webp"
                        @play="onPlay"
                        @pause="onPause"
                    >
                        <source src="https://resp.musesteamer2.com/steamer/videos/omniHuman-15.mp4" type="video/mp4">
                        Your browser does not support the video tag.
                    </video>
                    <button v-if="!isPlaying" @click="playVideo" class="play-button" aria-label="Play Video">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" width="48px" height="48px">
                            <path d="M8 5v14l11-7z"></path>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const videoPlayer = ref<HTMLVideoElement | null>(null);
const isPlaying = ref(false);

const playVideo = () => {
  if (videoPlayer.value) {
    videoPlayer.value.play();
  }
};

const onPlay = () => {
  isPlaying.value = true;
  if (videoPlayer.value) {
    videoPlayer.value.controls = true;
  }
};

const onPause = () => {
  isPlaying.value = false;
  if (videoPlayer.value) {
    videoPlayer.value.controls = false;
  }
};
</script>

<style scoped>
/* Hero Section */
.hero-section {
    background-color: #0D1117;
    text-align: center;
    padding: 100px 0;
    min-height: 600px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.hero-layout {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 40px;
}

.hero-text {
    max-width: 95%;
}

.hero-video {
    width: 100%;
    max-width:  95%;
}

.hero-section h1 {
    margin-bottom: 30px;
    font-size: 2.5em; /* Adjusted for new layout */
    line-height: 1.3;
    font-weight: 700;
}

.hero-section p {
    font-size: 1.1em;
    margin: 0 auto 40px auto;
    color: #cccccc;
}

.video-container {
    position: relative;
    width: 100%;
    padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
    height: 0;
    overflow: hidden;
    background-color: #000;
    border-radius: 10px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
}

.video-container video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
}

.play-button {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 10;
    background: rgba(0, 0, 0, 0.6);
    border: 2px solid white;
    border-radius: 50%;
    width: 80px;
    height: 80px;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: background-color 0.3s ease, transform 0.3s ease;
    padding: 0;
    padding-left: 5px; /* Optical alignment */
}

.play-button:hover {
    background-color: #ff4081; /* highlight-primary color */
    transform: translate(-50%, -50%) scale(1.1);
}

.play-button svg {
    fill: white;
}

@media (max-width: 768px) {
    .hero-section {
        padding: 80px 0;
    }
    .hero-section h1 {
        font-size: 2.2em;
    }
    .hero-section p {
        font-size: 1.0em;
    }
}

@media (max-width: 480px) {
    .hero-section h1 {
        font-size: 1.9em;
    }
}
</style>
