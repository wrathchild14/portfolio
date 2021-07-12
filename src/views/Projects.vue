<template>
  <div class="projects">
    <div class="title">Projects page</div>
    <v-container>
      <v-row>
        <v-col v-for="project in projects" :key="project.title" cols="4">
          <!-- <v-card height="200">
            <p>{{ project.title }}</p>
          </v-card> -->

          <v-card class="mx-auto" max-width="344">
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
              height="200px"
            ></v-img>

            <v-card-title> {{ project.title }} </v-card-title>

            <!-- <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle> -->

            <v-card-actions>
              <v-btn color="orange lighten-2" text :href="project.link" target="_blank">
                Explore 
              </v-btn>

              <v-spacer></v-spacer>

              <v-btn icon @click="project.show = !project.show">
                <v-icon>{{
                  project.show ? "mdi-chevron-up" : "mdi-chevron-down"
                }}</v-icon>
              </v-btn>
            </v-card-actions>

            <v-expand-transition>
              <div v-show="project.show">
                <v-divider></v-divider>

                <v-card-text>
                  {{ project.description }}
                </v-card-text>
              </div>
            </v-expand-transition>
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
      show: false,
      projects: [
        {
          title: "Compiler",
          description: "i did a combiler",
          img: "",
          show: false,
          link: "https://github.com/wrathchild14/compiler-java",
        },
        {
          title: "Website",
          description: "i did a webiste",
          img: "",
          show: false,
          link: "https://github.com/wrathchild14/movies-website-php",
        },
        {
          title: "Data structures",
          description: "i did a pathfinder",
          img: "",
          show: false,
          link: "https://github.com/wrathchild14/data-structures-java",
        },
        {
          title: "Game",
          description: "i did a game",
          img: "",
          show: false,
          link: "https://github.com/wrathchild14/game",
        },
        {
          title: "Cringe",
          description: "i did a cringe",
          img: "",
          show: false,
          link: "",
        },
      ],
    };
  },
};
</script>

<style>
</style>