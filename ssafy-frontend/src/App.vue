<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

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
    </v-app-bar>
    <!-- 데스크탑 버전시 다른 navbar 사용 -->
    <!-- 모바일 버전시 아래 navbar 사용 -->
    <mobileNavbar v-if="deviceType == 'MOBILE'"></mobileNavbar>
    <v-content>
      <v-container fluid>
        <router-view />
      </v-container>
    </v-content>
  </v-app>
</template>




<script>
import mobileNavbar from "./components/Navbar";

export default {
  name: "App",
  components: {
    mobileNavbar
  },
  data: () => ({
    deviceType: ""
  }),
  methods: {
    
  },
  mounted() {
    window.console.log(` 마운트 실행 `);
      window.console.log(`실행 `);
      window.console.log(this.deviceType);

      var windowWidth = $(window).width();
      if (windowWidth < 500) {
        this.deviceType = "MOBILE";
      } else {
        this.deviceType = "PC";
      }

      window.console.log(this.deviceType);
      window.console.log(` 마운트 종료 `);
  },
};
</script>
