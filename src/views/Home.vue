<template>
  <v-parallax src="night-city.jpeg" height="1200">
    <v-layout column align-center justify-center class="white--text">
      <h1
        class="white--text mb-2 display-1 text-xs-center"
        style="font-weight: 900; text-shadow: 3px 2px #000000"
      >
        Welcome to my Webiste
      </h1>
      <div
        class="white--text subheading mb-3 text-xs-center"
        style="font-weight: 900; text-shadow: 2px 2px #000000"
      >
        Jovan Prodanov 2021
      </div>
      <v-btn class="green darken-4" dark large to="/education">
        Get Started
      </v-btn>

      <v-dialog transition="dialog-top-transition" max-width="600">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="green darken-4" class="mt-2" dark large v-bind="attrs" v-on="on">about me</v-btn>
        </template>

        <template v-slot:default="dialog">
          <v-card>
            <v-card-title class="green darken-4">
              <span class="text-h5 white--text">Jovan Prodanov</span>
            </v-card-title>

            <v-list>
              <v-list-item>
                <v-list-item-action>
                  <v-icon>mdi-email</v-icon>
                </v-list-item-action>

                <v-list-item-content>
                  <v-list-item-title
                    >jovanprodanov123@gmail.com</v-list-item-title
                  >
                </v-list-item-content>
              </v-list-item>

              <v-divider inset></v-divider>

              <v-list-item>
                <v-list-item-action>
                  <v-icon>mdi-map-marker</v-icon>
                </v-list-item-action>

                <v-list-item-content>
                  <v-list-item-title>
                    Slovenia, Ljubljana 1000
                  </v-list-item-title>
                  <v-list-item-title>
                    Macedonia, Gevgelija 1480
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>

            <!-- <v-img
              src="https://picsum.photos/700?image=996"
              height="200px"
            ></v-img> -->
            <v-card-actions class="justify-end">
              <v-btn text @click="dialog.value = false">
                <v-icon>mdi-exit-to-app</v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>

    </v-layout>
  </v-parallax>
</template>

<script>
export default {
  name: "Home",

  components: {},
};
</script>
