<template>
  <NuxtLink
    class="p-2 rounded-lg group"
    :to="project.url"
    target="_blank"
    external
  >
    <div class="flex gap-4 items-center">
      <Icon aria-hidden="true" :name="project.icon" class="h-10 group-hover:text-primary-600 basis-1/6" />
      <div class="flex-1">
        <h3 class="text-sm font-medium group-hover:text-primary-600">
        {{ project.name }}
      </h3>
      <p class="text-gray-400 text-sm">{{ project.description }}</p>
      </div>
    </div>
  </NuxtLink>
</template>

<script setup>
defineProps({
  project: {
    type: Object,
    required: true,
  },
});
</script>
