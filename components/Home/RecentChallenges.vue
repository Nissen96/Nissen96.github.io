<template>
  <div>
    <h2 class="uppercase text-xs font-semibold text-gray-400 mb-6">
      RECENT CHALLENGES
    </h2>
    <p>My challenges are currently available with source and writeups (for most) from my GitHub: <a href="https://github.com/Nissen96/nc3-challs-2023/" target="_blank" class="underline">NC3 CTF 2023</a> and <a href="https://github.com/Nissen96/CTF-Challenges/" target="_blank" class="underline">DDC + other</a>. Note, some of these are for Danish CTFs and have been created in Danish.</p>
    <p>This page will later likely just contain an index of the challenges.</p>
    <ul class="space-y-16">
      <li v-for="(challenge, id) in challenges" :key="id">
        <AppChallengeCard :challenge="challenge" />
      </li>
    </ul>
    <div class="flex items-center justify-center mt-6 text-sm">
      <UButton
        label="All Challenges &rarr;"
        to="/challenges"
        variant="link"
        color="gray"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
const { data: challenges } = await useAsyncData("challenges-home", () =>
  queryContent("/challenges")
    .sort({ published: -1 })
    .limit(3)
    .only(["title", "description", "published", "slug", "_path"])
    .find()
);
</script>
