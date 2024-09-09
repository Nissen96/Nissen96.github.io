<template>
  <div class="space-y-6">
    <NuxtImg src="/avatar.png" alt="Nissen"
      class="ring-2 border ring-gray-200 border-gray-300 dark:ring-white/10 dark:border-gray-800 hover:ring-4 transition-all duration-300 bg-gray-200 dark:bg-gray-900 rounded-full h-12 w-12 sm:h-16 sm:w-16"
      sizes="48px sm:64px" placeholder format="webp" />
    <h1 class="text-xl font-bold tracking-tight text-gray-800 dark:text-gray-100">
      Nissen
    </h1>
    <p class="text-gray-900 dark:text-gray-400">
      Reverse engineer, malware analyst, digital forensic specialist.
    </p>
    <p class="text-gray-900 dark:text-gray-400">
      By day, I investigate cyber crime and disrupt cyber criminal networks.<br>
      By night, I torture myself with cursed CTF challenges with <a href="https://brunnerne.dk" target="_blank" class="underline">Brunnerne</a> to satisfy that deep, insatiable craving for fake internet points.
    </p>
    <p class="text-gray-900 dark:text-gray-400">
      This site is my space to gather and share my projects, CTF challenges, writeups, and any technical insights I uncover along the way.
    </p>
  </div>
</template>

<script setup>
useSeoMeta({
  title: "Nissen",
  description:
    "I'm Nissen, a cyber security nerd who loves reverse engineering, malware analysis, and digital forensics.",
});
</script>
