<template>
  <section id="faq" class="section-block bg-dark">
    <div class="container">
      <h2>Frequently Asked <span class="highlight-secondary">Questions</span></h2>
      <div class="faq-grid">
        <div v-for="(item, index) in faqItems" :key="index" class="faq-item">
          <div class="faq-question">
            <h3>{{ item.question }}</h3>
          </div>
          <div class="faq-answer">
            <p>{{ item.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const faqItems = ref([
  {
    question: 'What is OmniHuman 1.5 and what does it do?',
    answer: 'OmniHuman 1.5 is an advanced AI-powered character animation platform. It specializes in creating expressive, lifelike digital avatars from a single photo and a voice recording, using a sophisticated system that combines Multimodal Large Language Models with Diffusion Transformers for realistic results.'
  },
  {
    question: 'What kind of content can I create with OmniHuman?',
    answer: 'The platform is highly versatile. You can create rhythmic and soulful digital singers for music videos, generate emotionally rich digital actors for cinematic scenes, and even produce complex multi-person dialogues and performances by routing different audio tracks to characters in a single frame.'
  },
  {
    question: 'Who is OmniHuman designed for?',
    answer: 'OmniHuman is designed for a wide range of creators, including animators, filmmakers, game developers, and content creators. It streamlines the animation workflow, enhances creative expression, and significantly reduces the time and cost associated with traditional character animation.'
  },
  {
    question: 'How does OmniHuman create such realistic animations?',
    answer: 'OmniHuman utilizes a unique "Brain-Like" reasoning system. It processes audio to understand emotional subtext and generates performances with a full dramatic range without needing explicit text prompts. This allows for nuanced animations that capture everything from subtle expressions to dynamic emotional shifts.'
  }
]);
</script>

<style scoped>
.faq-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
  margin-top: 40px;
}

.faq-item {
  background-color: #2d2d2d;
  padding: 25px;
  border-radius: 8px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.3);
  display: flex;
  flex-direction: column;
}

.faq-question h3 {
  color: #00bcd4;
  font-size: 1.3em;
  margin-bottom: 15px;
  font-weight: 700;
}

.faq-answer p {
  color: #cccccc;
  font-size: 1em;
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 768px) {
  .faq-grid {
    grid-template-columns: 1fr;
  }
}
</style>
