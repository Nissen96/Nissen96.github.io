<template>
  <main>
    <AppHeader class="mb-6 md:mb-10" title="Projects" :description="description" />
    <div class="space-y-4">
      <AppProjectCard
        v-for="(project, id) in projects"
        :key="id"
        :project="project"
      />
    </div>
  </main>
</template>

<script setup>
const description = "Some of my more useful tools, all open source and available through my GitHub. Most are scripts to automate certain tasks within forensics and reverse engineering.";
useSeoMeta({
  title: "Projects | Nissen",
  description,
});

const { data: projects } = await useAsyncData("projects-all", () =>
  queryContent("/projects").sort({ title: -1 }).find()
);
</script>
