<template>
  <v-app>
    <!-- 데스크탑 버전시 다른 navbar 사용 -->
    <navbar v-if="!$vuetify.breakpoint.xs" ></navbar>
    <!-- 모바일 버전시 아래 navbar 사용 -->
    <mobileNavbar v-if="$vuetify.breakpoint.xs" ></mobileNavbar>
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
    
  }),
};
</script>
