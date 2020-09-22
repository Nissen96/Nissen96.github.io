<template>
  <v-row justify="center">
    <v-col cols="12" md="8" lg="6">
      <v-row class="text-center">
        <v-col>
          <h1>Alexander Nissen</h1>
          <h2>Projects</h2>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="4">
          <ProjectCard title="easyGraph" img="easyGraph.png" link="/easyGraph">
            Easy to use tool for drawing both directed and undirected graphs
          </ProjectCard>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "Home",
}
</script>
