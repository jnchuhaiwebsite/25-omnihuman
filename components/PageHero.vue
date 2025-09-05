<template>
  <div class="text-center ">
    <h1 class="text-3xl font-extrabold tracking-tight sm:text-4xl lg:text-5xl bg-gradient-to-r from-[#ff4081] via-[#ff4081] to-[#ff4081] text-transparent bg-clip-text py-2">
      <span class="block">{{ title }}</span>
    </h1>
    <p v-if="subtitle" class="mx-auto mt-6 max-w-4xl text-[1.2rem] tracking-tight text-[#8b949e]">
      {{ subtitle }}
    </p>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title: string
  subtitle: string
}

defineProps<Props>()
</script> 