<template>
  <div class="projects">
    <v-container class="mt-5">
      <v-row>
        <v-col v-for="project in projects" :key="project.title" md="4" xs="12">
          <v-card class="mx-auto" width="344">
            <v-img :src="project.img" height="200px"></v-img>

            <v-card-title class="green--text">
              {{ project.title }}
            </v-card-title>

            <v-card-actions>
              <v-btn text :href="project.link" target="_blank">
                <!-- Explore -->
                <v-icon large left>mdi-github</v-icon>
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
          description:
            "I develope my own compiler in the computer language Java for a languange named .pins21.",
          img: "compiler.jpeg",
          show: false,
          link: "https://github.com/wrathchild14/compiler-java",
        },
        {
          title: "Website",
          description:
            "Developed a website using MVC, php and MySQL for the database.",
          img: "https://lequid.es/blog/wp-content/uploads/2018/05/WHAT-IS-THE-CORPORATE-WEBSITE.jpg",
          show: false,
          link: "https://github.com/wrathchild14/movies-website-php",
        },
        {
          title: "Data structures",
          description:
            "In java, I had played around and developed the following data strucutres: Tree23, Binary Search Tree, Hash Tree, SkipList...",
          img: "data:image/png;base64,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",
          show: false,
          link: "https://github.com/wrathchild14/data-structures-java",
        },
        {
          title: "Game",
          description:
            "Developed a game in WebGL, which i called RipNOff. To play it press on Game on the left menu",
          img: "ripnoff.png",
          show: false,
          link: "https://github.com/wrathchild14/game",
        },
        {
          title: "Drug problem in Europe",
          description:
            "With a couple of friends we analyzed the data available regarding drugs in Europe, build various prediction models to better understand the problem",
          img: "https://raw.githubusercontent.com/danilo1214/PR20ddpdjphv/master/ECSTASYLINREG.png",
          show: false,
          link: "https://github.com/danilo1214/PR20ddpdjphv",
        },
        {
          title: "This website",
          description:
            "Made a challenge for me to learn a new technology and made this webiste with Vuetify js and Vue js",
          img: "favicon.ico",
          show: false,
          link: "https://github.com/wrathchild14/portfolio",
        },

      ],
    };
  },
};
</script>

<style>
</style>