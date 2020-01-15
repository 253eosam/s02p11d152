<template>
      <v-navigation-drawer  class="indigo darken-2" :mini-variant.sync="mini" v-model="drawer" dark permanent app>
      <template v-slot:prepend>
        <v-list-item>
        <v-list-item-avatar>
          <v-img :src="getImgUrl(profile.img)"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>{{profile.name}} <br> {{profile.email}} </v-list-item-title>

        <v-btn
          icon
          @click.stop="mini = !mini"
        >
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>
      </template>

      <v-list nav>
        <v-list-item v-for="item in items" :key="item.title" link @click="movePageByNav(item.title)">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</template>

<script>
  export default {
     data: () => ({
           drawer: true, mini: true,
    items: [
          { title: 'Home', icon: 'home' },
          { title: 'Post', icon: 'insert_comment' },
          { title: 'Portfolio', icon: 'menu_book' },
        ],
    profile : {
      name : "이성준",
      email : "dhzm2aud@naver.com",
      img : "profile"
    }
  }),
    methods:{
      movePageByNav(pageName){
        pageName = pageName.toLowerCase();
        var toPage = "";
        if(`login` == pageName){
          toPage = `login`;
        }else if(`post` == pageName){
          toPage = `post`;
        }else if(`portfolio` == pageName){
          toPage = `portfolio`;
        }
        this.$router.push(`/${toPage}`);
      },
      getImgUrl(img) {
			return require(`../assets/${img}.jpg`)
		}
    }
  }
</script>