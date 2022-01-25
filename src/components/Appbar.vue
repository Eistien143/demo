<template>
  <v-app-bar app color="primary" dark>
    <v-btn elevation="0" text>Arun Gamer</v-btn>
    <v-spacer></v-spacer>

    <router-link
      v-for="(link, i) in links"
      :key="i"
      :to="link.path"
      class="ma-2 text-decoration-none white--text"
      >{{ link.title }}</router-link
    >
  </v-app-bar>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          path: "/",
          title: "Home",
        },
        {
          path: "/blogs",
          title: "Blog",
        },
        {
          path: "/about",
          title: "About",
        },
      ],
    };
  },
};
</script>

<style></style>
