<template>
  <div class="projects">
    <h1>Projects page</h1>
    <v-container>
      <v-row>
        <v-col v-for="project in projects" :key="project.title" cols="4">
          <v-card height="200">
            <p>{{ project.title }}</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Compiler",
        },
        {
          title: "Website",
        },
        {
          title: "Pathfind",
        },
        {
          title: "Game",
        },
        {
          title: "Cringe",
        },
      ],
    };
  },
};
</script>

<style>
</style>