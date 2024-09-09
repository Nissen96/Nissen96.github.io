<template>
  <main>
    <AppHeader class="mb-12" title="Challenges" :description="description" />
    <p>My challenges are currently available with source and writeups (for most) from my GitHub: <a href="https://github.com/Nissen96/nc3-challs-2023/" target="_blank" class="underline">NC3 CTF 2023</a> and <a href="https://github.com/Nissen96/CTF-Challenges/" target="_blank" class="underline">DDC + other</a>. Note, some of these are for Danish CTFs and have been created in Danish.</p>
    <p>This page will later likely just contain an index of the challenges.</p>
    <ul class="space-y-16">
      <li v-for="(challenge, id) in challenges" :key="id">
        <AppChallengeCard :challenge="challenge" />
      </li>
    </ul>
  </main>
</template>

<script setup>
const description =
  "CTF challenges I have created.";
useSeoMeta({
  title: "CTF Challenges | Nissen",
  description,
});

const { data: challenges } = await useAsyncData("all-challenges", () =>
  queryContent("/challenges").find()
);
</script>
