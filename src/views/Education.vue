<template>
  <div class="education">
    <v-row>
      <v-card class="mx-auto" max-width="600" min-width="500">
        <v-card-title class="grey darken-3 white--text">
          <span class="text-h6">
            Finished courses at
            <a class="white--text" href="https://www.fri.uni-lj.si/sl" target="_blank">FRI</a>
          </span>
          <v-spacer></v-spacer>
          <v-btn
            :outlined="interval == null"
            :color="interval == null ? 'white' : 'red'"
            dark
            depressed
            @click="interval == null ? start() : stop()"
          >
            Play/Stop
          </v-btn>
        </v-card-title>
        <v-card-text class="py-0">
          <v-timeline dense>
            <v-slide-x-reverse-transition group hide-on-leave>
              <v-timeline-item
                v-for="item in items"
                :key="item"
                color="green darken-3"
                small
                fill-dot
              >
                <v-alert
                  :value="true"
                  class="white--text"
                  dense
                  icon="mdi-check-circle"
                  color="success darken-3"
                >
                  {{ item }}
                </v-alert>
              </v-timeline-item>
            </v-slide-x-reverse-transition>
          </v-timeline>
        </v-card-text>
      </v-card>

      <v-card class="mx-auto" max-width="600" min-width="500">
        <v-card-title class="grey darken-3 white--text">
          <span class="text-h6">Personal Interests </span>
          <v-spacer></v-spacer>
          <v-btn
            :outlined="interval_personal == null"
            :color="interval_personal == null ? 'white' : 'red'"
            dark
            depressed
            @click="
              interval_personal == null ? start_personal() : stop_personal()
            "
          >
            Play/Stop
          </v-btn>
        </v-card-title>
        <v-card-text class="py-0">
          <v-timeline dense>
            <v-slide-x-reverse-transition group hide-on-leave>
              <v-timeline-item
                v-for="item in items_personal"
                :key="item"
                color="blue darken-2"
                small
                fill-dot
              >
                <v-alert
                  :value="true"
                  class="white--text"
                  dense
                  icon="mdi-information"
                  color="info darken-3"
                >
                  {{ item }}
                </v-alert>
              </v-timeline-item>
            </v-slide-x-reverse-transition>
          </v-timeline>
        </v-card-text>
      </v-card>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          key: "College: Fakulteta za racunalnistvo in informatike",
          subjects: [
            "Introduction to Computer Science",
            "Programming 1/2",
            "Databases",
            "Computer Architecture",
            "Computer Communications",
            "Mathematics",
            "Discrete Structures",
            "Probability and Staticstics",
            "Algorithms and Data Strucutres 1/2",
            "Artificial Intelligence",
            "Data Mining",
            "Operating Systems",
            "Compilers and Virtual Machines",
            "Communications Protocols and Network Security",
            "Testing and Quality",
            "Computer Graphics",
            "Information Systems",
            "Web Technologies",
          ],
        },
        {
          key: "Personal interests",
          subjects: [
            "Vue js",
            "Vuetify",
            "Node js",
            "OpenGL",
            "Unreal Engine",
            "Data Science",
            "Machine Learning",
            "AI",

          ],
        },
      ],

      interval: null,
      items: [],
      interval_personal: null,
      items_personal: [],
    };
  },

  beforeDestroy() {
    this.stop();
  },

  methods: {
    addEvent() {
      this.items.push(this.cards[0].subjects.shift());
    },
    start() {
      this.interval = setInterval(this.addEvent, 500);
    },
    stop() {
      clearInterval(this.interval);
      this.interval = null;
    },

    addEvent_personal() {
      this.items_personal.push(this.cards[1].subjects.shift());
    },
    start_personal() {
      this.interval_personal = setInterval(this.addEvent_personal, 500);
    },
    stop_personal() {
      clearInterval(this.interval_personal);
      this.interval_personal = null;
    },
  },
};
</script>

<style>
</style>