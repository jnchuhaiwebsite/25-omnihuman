<template>
    <section id="features" class="section-block bg-dark">
        <div class="container">
            <h2>Core <span class="highlight-primary">Features</span></h2>
            <p class="subtitle">OmniHuman 1.5 is packed with powerful features designed to streamline the animation process and enhance creative expression, delivering unparalleled realism and efficiency.</p>
            <div class="features-list">
                <div v-for="(feature, index) in features" :key="index" class="feature-item">
                    <div class="video-container">
                        <video 
                            :ref="el => { if (el) videoPlayers[index] = el }"
                            :poster="feature.image"
                            :src="feature.videoSrc" 
                            preload="none"
                            playsinline 
                            class="feature-video"
                            @play="onPlay(index)"
                        >
                        </video>
                        <div v-if="!isPlaying[index]" class="play-button-overlay" @click="playVideo(index)">
                            <svg class="play-icon" viewBox="0 0 24 24">
                                <path fill="currentColor" d="M8,5.14V19.14L19,12.14L8,5.14Z" />
                            </svg>
                        </div>
                    </div>
                    <div class="text-container">
                        <h3>{{ feature.title }}</h3>
                        <p>{{ feature.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, onBeforeUpdate } from 'vue';

const features = ref([
    {
        title: 'Context-Aware Audio-Driven Animation',
        description: 'Unlock true-to-life character performances with OmniHuman. Our pioneering context-aware animation goes beyond basic lip-sync, interpreting the deep emotional and semantic nuances of any audio to bring an unprecedented level of realism to every scene.',
        image: 'https://resp.omnihuman-15.com/ohuman/image/Context-Aware-Audio-Driven-Animation.webp',
        videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Context-Aware-Audio-Driven-Animation.mp4' // Placeholder
    },
    {
        title: 'Text-Guided Multimodal Animation',
        description: 'Take complete creative control with OmniHuman\'s text-guided animation. Our state-of-the-art framework flawlessly follows your text prompts, giving you the power to direct everything from camera movements to specific character actions, all while maintaining perfect audio sync.',
        image: 'https://resp.omnihuman-15.com/ohuman/image/Text-Guided-Multimodal-Animation.webp',
        videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Text-Guided-Multimodal-Animation.mp4' // Placeholder
    },
    {
        title: 'Multi-Person Scene Performance',
        description: 'Effortlessly create complex, dynamic group scenes with OmniHuman. Our advanced framework intelligently routes separate audio tracks to the correct characters, generating seamless multi-person dialogues and captivating ensemble performances.',
        image: 'https://resp.omnihuman-15.com/ohuman/image/Multi-Person-Scene-Performance2.webp',
        videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Multi-Person-Scene-Performance2.mp4' // Placeholder
    },
    {
        title: 'More Results on Diverse Inputs',
        description: 'Unleash your imagination on any character style. OmniHuman showcases incredible versatility by generating high-quality, synchronized animations for a diverse range of subjects—from realistic animals and humans to stylized cartoons.',
        image: 'https://resp.omnihuman-15.com/ohuman/image/More-Results-on-Diverse-Inputs.webp',
        videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/More-Results-on-Diverse-Inputs.mp4' // Placeholder
    }
]);

const videoPlayers = ref<HTMLVideoElement[]>([]);
const isPlaying = ref(features.value.map(() => false));

onBeforeUpdate(() => {
  videoPlayers.value = [];
});

const playVideo = (index: number) => {
  const video = videoPlayers.value[index];
  if (video) {
    video.muted = false;
    video.controls = true;
    video.play();
  }
};

const onPlay = (index: number) => {
  isPlaying.value[index] = true;
};
</script>

<style scoped>
.features-list {
    display: flex;
    flex-direction: column;
    gap: 50px;
    margin-top: 40px;
}

.feature-item {
    display: flex;
    gap: 30px;
    background-color: #2d2d2d;
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    align-items: center;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
}

.feature-item:nth-child(even) {
    flex-direction: row-reverse;
}

.video-container {
    flex: 1;
    min-width: 300px;
    position: relative;
    cursor: pointer;
}

.feature-video {
    width: 100%;
    border-radius: 8px;
    display: block;
}

.text-container {
    flex: 1;
    text-align: left;
}

.play-button-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.4);
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 8px;
    transition: opacity 0.3s ease;
}

.play-button-overlay:hover {
    background-color: rgba(0, 0, 0, 0.6);
}

.play-icon {
    width: 70px;
    height: 70px;
    color: rgba(255, 255, 255, 0.9);
    transition: transform 0.2s ease;
}

.play-button-overlay:hover .play-icon {
    transform: scale(1.1);
}

.feature-item h3 {
    color: #ff4081;
    font-size: 1.8em;
    margin-bottom: 15px;
}

.feature-item p {
    font-size: 1em;
    color: #ccc;
    line-height: 1.6;
}

@media (max-width: 992px) {
    .feature-item, .feature-item:nth-child(even) {
        flex-direction: column;
    }
    .text-container {
        text-align: center;
        margin-top: 20px;
    }
}

@media (max-width: 768px) {
    .feature-item {
        padding: 20px;
    }
    .feature-item h3 {
        font-size: 1.5em;
    }
    .feature-item p {
        font-size: 0.9em;
    }
}
</style>
