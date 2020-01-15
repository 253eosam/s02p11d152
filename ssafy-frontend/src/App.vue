<template>
  <v-app>
    <!-- 데스크탑 버전시 다른 navbar 사용 -->
    <navbar v-if="deviceType == `PC`"></navbar>
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
import mobileNavbar from "./components/MoblieNavbar";
import navbar from "./components/Navbar";

export default {
  name: "App",
  components: {
    mobileNavbar,
    navbar
  },
  data: () => ({
    deviceType: ""
  }),
  methods: {
    
  },
  mounted() {
      var windowWidth = $(window).width();
      if (windowWidth < 500) {
        this.deviceType = "MOBILE";
      } else {
        this.deviceType = "PC";
      }
  },
};
</script>
