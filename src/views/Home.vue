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
      <v-btn class="green darken-4 mt-5" dark large to="/education">
        Get Started
      </v-btn>
    </v-layout>
  </v-parallax>
</template>

<script>
export default {
  name: "Home",

  components: {},
};
</script>
