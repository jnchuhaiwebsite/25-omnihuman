<template>
    <section id="use-cases" class="section-block bg-dark">
        <div class="container">
            <h2>Use <span class="highlight-secondary">Cases</span></h2>
            <p class="subtitle">From entertainment and social media to education and film production, see how OmniHuman 1.5 is being applied across various industries to create compelling content.</p>
            <div class="case-list">
                <div v-for="(useCase, index) in useCases" :key="index" class="case-item">
                    <div class="video-container">
                        <video 
                            :ref="el => { if (el) videoPlayers[index] = el }"
                            :poster="useCase.image"
                            :src="useCase.videoSrc" 
                            preload="none"
                            playsinline 
                            class="case-video"
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
                        <h3>{{ useCase.title }}</h3>
                        <p>{{ useCase.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { ref, onBeforeUpdate } from 'vue';

const useCases = ref([
  {
    title: 'Rhythmic Performances',
    image:'https://resp.omnihuman-15.com/ohuman/image/Rhythmic-Performances.webp',
    description: 'Experience the future of music with OmniHuman. We transform a single image into a soulful digital singer, creating performances rich with genuine musical expression. From intimate ballads to high-energy concerts, OmniHuman captures every nuance far beyond simple lip-sync.',
    videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Rhythmic-Performances.mp4'
  },
  {
    title: 'Emotional Performances',
    image:'https://resp.omnihuman-15.com/ohuman/image/Emotional-Performances.webp',
    description: "Bring your stories to life with OmniHuman's digital actors. Our AI analyzes the emotional heart of your audio to generate powerfully cinematic performances, capturing a full spectrum of drama from explosive rage to quiet sorrow, all from just one image.",
    videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Emotional-Performances.mp4'
  },
  {
    title: 'Multi-Person Scene Performance',
    image:'https://resp.omnihuman-15.com/ohuman/image/Multi-Person-Scene-Performance.webp',
    description: 'Directing complex group scenes has never been easier. OmniHuman effortlessly orchestrates dynamic multi-character dialogues and ensemble performances, intelligently syncing each voice to the right digital actor for a seamless and believable interaction.',
    videoSrc: 'https://resp.omnihuman-15.com/ohuman/video/Multi-Person-Scene-Performance.mp4'
  }
]);

const videoPlayers = ref<HTMLVideoElement[]>([]);
const isPlaying = ref(useCases.value.map(() => false));

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
.case-list {
    display: flex;
    flex-direction: column;
    gap: 50px;
    margin-top: 40px;
}

.case-item {
    display: flex;
    gap: 30px;
    background-color: #2d2d2d;
    padding: 30px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    align-items: center;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.case-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
}

.case-item:nth-child(even) {
    flex-direction: row-reverse;
}

.video-container {
    flex: 1;
    min-width: 300px;
    position: relative;
    cursor: pointer;
}

.case-video {
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
    cursor: pointer;
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

.case-item h3 {
    color: #ff4081;
    font-size: 1.8em;
    margin-bottom: 15px;
}

.case-item p {
    font-size: 1em;
    color: #ccc;
    line-height: 1.6;
}

@media (max-width: 992px) {
    .case-item, .case-item:nth-child(even) {
        flex-direction: column;
    }
    .text-container {
        text-align: center;
        margin-top: 20px;
    }
}

@media (max-width: 768px) {
    .case-item {
        padding: 20px;
    }
    .case-item h3 {
        font-size: 1.5em;
    }
    .case-item p {
        font-size: 0.9em;
    }
}
</style>
