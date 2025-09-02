<template>
    <section id="users-value" class="section-block">
        <div class="container">
            <h2>Target Users & <span class="highlight-primary">Value</span></h2>
            <p class="subtitle">Learn who can benefit most from OmniHuman 1.5 and the unique value it provides to content creators, developers, and production studios.</p>
            <div class="content-pair">
                <div class="half-block">
                    <h3>🎯 Target Users:</h3>
                    <ul>
                        <li>Content creators (YouTubers, TikTok/Douyin creators)</li>
                        <li>Virtual streamers & KOLs</li>
                        <li>Game & metaverse developers</li>
                        <li>Education & training organizations</li>
                        <li>Film & media production studios</li>
                    </ul>
                </div>
                <div class="half-block">
                    <h3>💡 User Value:</h3>
                    <ul>
                        <li><strong>Low-cost, high-quality:</strong> Allows one image + audio to produce minute-long videos efficiently.</li>
                        <li><strong>High flexibility:</strong> Text prompts provide precise action & camera control.</li>
                        <li><strong>Cross-domain adaptability:</strong> Works for humans, animals, cartoons, and multi-character scenes.</li>
                        <li><strong>Strong emotional expressiveness:</strong> Captures nuanced emotions and gestures from speech.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
/* Content Pair */
.content-pair {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    justify-content: space-between;
}

.content-pair > * {
    flex: 1;
    min-width: 400px; /* Prevent content from becoming too narrow */
}

/* Half Width Blocks for Users & Value */
.half-block {
    padding: 30px;
    background-color: #2a2a2a;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.half-block:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

.half-block h3 {
    text-align: left;
    margin-bottom: 25px;
    color: #00bcd4; /* Subtitle accent color */
    font-size: 1.5em;
}

@media (max-width: 768px) {
    .content-pair {
        flex-direction: column;
    }
    .content-pair > * {
        min-width: unset;
        width: 100%;
    }
}
</style>
