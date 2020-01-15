<template>
  <v-app-bar app dark color="indigo darken-2">
    <div class="d-flex align-center">
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2"
        contain
        src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
        transition="scale-transition"
        width="40"
      />
      <v-toolbar-title>My Blog</v-toolbar-title>

      <v-img
        alt="Vuetify Name"
        class="shrink mt-1 hidden-sm-and-down"
        contain
        min-width="100"
        src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
        width="100"
      />
    </div>

    <v-spacer></v-spacer>

    <v-btn href="https://github.com/vuetifyjs/vuetify/releases/latest" target="_blank" text>
      <span class="mr-2">Latest Release</span>
      <v-icon>mdi-open-in-new</v-icon>
    </v-btn>
    <template v-slot:extension>
      <v-tabs align-with-title background-color="transparent">
        <v-tab @click="movePageByNav(`home`)">home</v-tab>
        <v-tab @click="movePageByNav(`post`)">post</v-tab>
        <v-tab @click="movePageByNav(`portfolio`)">portfolio</v-tab>
      </v-tabs>
    </template>
  </v-app-bar>
</template>

<script>
export default {
  name: "navbar",
  data() {
    return {
      pages:["hoem","post","portfolio"]
    };
  },
  methods: {
    movePageByNav(pageName) {
      pageName = pageName.toLowerCase();
      var toPage = "";
      if (`login` == pageName) {
        toPage = `login`;
      } else if (`post` == pageName) {
        toPage = `post`;
      } else if (`portfolio` == pageName) {
        toPage = `portfolio`;
      }
      this.$router.push(`/${toPage}`);
    }
  }
};
</script>