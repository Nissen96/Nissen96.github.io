<template>
  <v-card :href="link">
    <v-img
      :src="img"
      :aspect-ratio="1"
      gradient="to bottom, rgba(0,0,0,0), rgba(0,0,0,.1)"
    />
    <v-card-title v-text="title" />
    <v-card-text>
      <slot />
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    title: { type: String, default: "" },
    img: { type: String, default: "" },
    link: { type: String, default: "" },
  },
}
</script>
