<template>
  <v-card>
    <v-navigation-drawer expand-on-hover color="indigo darken-2" dark permanent app>
      <template v-slot:prepend>
        <v-list-item>
          <v-list-item-avatar>
            <v-img :src="getImgUrl(profile.img)"></v-img>
          </v-list-item-avatar>
          <v-list-item link two-line>
            <v-list-item-content>
              <v-list-item-title class="title">{{profile.name}}</v-list-item-title>
              <v-list-item-subtitle>{{profile.email}}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list-item>
      </template>
      <v-divider></v-divider>

      <v-list nav dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          @click="movePageByNav(item.title)"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
export default {
  name: "Navbar",
  data: () => ({
    items: [
      { title: "Home", icon: "home" },
      { title: "Post", icon: "insert_comment" },
      { title: "Portfolio", icon: "menu_book" }
    ],
    profile: {
      name: "이성준",
      email: "dhzm2aud@naver.com",
      img: "profile"
    }
  }),
  methods: {
    movePageByNav(pageName) {
      pageName = pageName.toLowerCase();
      console.log(this.$component);
      var toPage = "";
      if (`login` == pageName) {
        toPage = `login`;
      } else if (`post` == pageName) {
        toPage = `post`;
      } else if (`portfolio` == pageName) {
        toPage = `portfolio`;
      }
      this.$router.push(`/${toPage}`);
    },
    getImgUrl(img) {
      return require(`../assets/${img}.jpg`);
    }
  }
};
</script>
