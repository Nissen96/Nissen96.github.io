<template>
  <div>
    <h2 class="uppercase text-xs font-semibold text-gray-400 mb-6">
      RECENT WRITEUPS
    </h2>
    <p>All writeups are currently still on my old page and will be moved at a later point in time: <a href="https://nissen96.github.io/CTF-writeups/" target="_blank" class="underline">Writeup site</a></p>
    <ul class="space-y-16">
      <li v-for="(writeup, id) in writeups" :key="id">
        <AppWriteupCard :writeup="writeup" />
      </li>
    </ul>
    <div class="flex items-center justify-center mt-6 text-sm">
      <UButton
        label="All Writeups &rarr;"
        to="/writeups"
        variant="link"
        color="gray"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
const { data: writeups } = await useAsyncData("writeups-home", () =>
  queryContent("/writeups")
    .sort({ published: -1 })
    .limit(3)
    .only(["title", "description", "published", "slug", "_path"])
    .find()
);
</script>
