<template>
  <main>
    <AppHeader class="mb-16" title="Writeups" :description="description" />
    <p>All writeups are currently still on my old page and will be moved at a later point in time: <a href="https://nissen96.github.io/CTF-writeups/" target="_blank" class="underline">Writeup site</a></p>
    <ul class="space-y-16">
      <li v-for="(writeup, id) in writeups" :key="id">
        <AppWriteupCard :writeup="writeup" />
      </li>
    </ul>
  </main>
</template>

<script setup>
const description =
  "Writeups of interesting CTF challenges I have solved and/or created.";
useSeoMeta({
  title: "CTF Writeups | Nissen",
  description,
});

const { data: writeups } = await useAsyncData("all-writeups", () =>
  queryContent("/writeups").sort({ published: -1 }).find()
);
</script>
