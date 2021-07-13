<template>
  <v-navigation-drawer :mini-variant.sync="mini" permanent app>
      
    <!-- @click make popup for my picture and information -->
    <v-list-item class="px-2">
      <v-list-item-avatar>
        <!-- cringe -->
        <v-img src="../../public/pikachu.jpg"></v-img>
      </v-list-item-avatar>

      <v-list-item-title>Jovan Prodanov</v-list-item-title>

      <v-btn icon @click.stop="mini = !mini">
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense>
      <v-list-item v-for="item in items" :key="item.title" link router :to="item.path">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-list-item href="https://wrathchild14.github.io/" target="_blank">
        <v-list-item-icon>
          <v-icon>mdi-alien</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>Play Rip & Off</v-list-item-title>
        </v-list-item-content>
      </v-list-item>

    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "Home", icon: "mdi-home", path: "/" },
        { title: "Education", icon: "mdi-book-open-variant", path: "/education" },
        { title: "Projects", icon: "mdi-desktop-mac", path: "/projects" },
        // { title: "Game", icon: "mdi-alien", path: "/game"}, // temp
        { title: "Contact", icon: "mdi-account", path: "/about" },
      ],
      mini: true,
    };
  },
};
</script>