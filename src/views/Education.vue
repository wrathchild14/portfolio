<template>
  <div class="education">
    <v-container class="py-8 px-5" fluid>
      <v-row>
        <v-col v-for="card in cards" :key="card.key" cols="12">
          <v-card>
            <v-subheader class="text-h5">{{ card.key }}</v-subheader>

            <v-list two-line>
              <template v-for="n in card.subjects">
                <v-list-item :key="n.key">
                  <v-list-item-content> - {{ n }} </v-list-item-content>
                </v-list-item>
              </template>
            </v-list>
          </v-card>
        </v-col>
      </v-row>

      <v-btn class="green darken-4 mt-5" dark large to="/projects">
        To Projects
      </v-btn>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          key: "Highschool: Josif Josifovski",
          subjects: ["Nothing", "Special"],
        },
        {
          key: "College: Fakulteta za racunalnistvo in informatiko",
          subjects: [
            "Artificial Intelligence",
            "Data Mining",
            "Operating Systems",
            "Compilers and Virtual Machines",
            "Algorithms and Data Strucutres 1/2",
            "Computer Networks and Security",
          ],
        },
        {
          key: "Personal interests",
          subjects: ["Vue js", "Vuetify", "Node js"],
        },
      ],
    };
  },
};
</script>

<style>
</style>