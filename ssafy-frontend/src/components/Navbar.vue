<template>
      <v-navigation-drawer expand-on-hover class="primary accent-4" dark permanent app>
      <template v-slot:prepend>
        <v-list>
          <v-list-item>
            <v-list-item-avatar>
              <v-img :src="profile.img"></v-img>
            </v-list-item-avatar>
          </v-list-item>

          <v-list-item link two-line>
            <v-list-item-content>
              <v-list-item-title class="title">{{profile.name}}</v-list-item-title>
              <v-list-item-subtitle>{{profile.email}}</v-list-item-subtitle>
            </v-list-item-content>
            <v-list-item-action>
              <v-icon>mdi-menu-down</v-icon>
            </v-list-item-action>
          </v-list-item>
        </v-list>
      </template>

      <v-list nav dense>
        <v-list-item v-for="item in items" :key="item.title" link>
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
    items: [
          { title: 'BlogTitle', icon: 'home' },
          { title: 'Post', icon: 'insert_comment' },
          { title: 'Portfolio', icon: 'menu_book' },
        ],
    profile : {
      name : "이성준",
      email : "dhzm2aud@naver.com",
      img : "https://s3.us-west-2.amazonaws.com/secure.notion-static.com/b1913204-191d-4cc5-8ee2-6f00a1171641/KakaoTalk_20190720_010602920.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=ASIAT73L2G45G5VDDLGW%2F20200115%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200115T020632Z&X-Amz-Expires=86400&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEN7%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLXdlc3QtMiJHMEUCIBDUnztzKun5OgP%2FKI%2Bo2Ri9z0PMSRLKo7XpNh78qzQdAiEAqw50H2QUrZKss86gECe4%2FauCqSeTjUAsH9rpFYZFPfkqtAMIZxAAGgwyNzQ1NjcxNDkzNzAiDHc%2ByUf1LOG4lGBQpSqRA3Uggq8rj3cSK9VfTAJu4st1CrLRpXlq8zDrZqnytT7MyIL5yxqoAf36QjMx3%2F%2FW4AocUyL1Z5rrTtujjuAvk0Njunf%2FocDu0pduwnEAZkQXRz8ze35Hk95KmaSavKLV6jyXL09OxgfYWXEI3aN6qKBxgNJ8L5I78gtVOrdtMCHreUqegpe9x1eHso1lUS4kRN7VTIMkmaSGhBCZhXLYvmQPA2Zu%2FyHW9rqtQlB2JqREatjbGefAM4nNHMbFl3ZpjfjPXGmqufhipcdegpfcUnOaClhezcxsGHFbPg8jf%2FKOff2WArnbJ5nJo%2Fq7b%2Fy%2BgjPLLzm8PATFCvhL%2BIv4qNaSXtMm57nQHoytpbhwdzYDJUX%2BZd0wev8yBSKJr6Ekgp1GY0%2Br%2BZRS4k9xJqFD%2FMa8f%2FTXCGYASGneAVkG%2FbBIBfFx8Eu%2BXK6ja0PmycVGRi8aS477UGSiSlO93xgJG5i5b3dNWGsfBkcoHgA0yoohoTs4u%2Fw7mDWNMa7B8Py0anAcl5bET61dszokjUewTEYIMNfv%2BPAFOusBmoTt4LaWxJLf7tsVdH4e0n3FbJ3upH%2FOgobapglF4MwX0DxbsrTt38v4N1itlc7jeWwKKs%2FZGkWNBkrfR5RM36tVbcyJFYx5AdImWq1xtZ%2BDF%2BDe5VhCvbvXCF2nYK14%2BmsyqRGKvoSZaBcl2TDc%2FaA1XDzS0toxZGB16JdrFzzS8IHMsZ99ApkUDqNaS64HnA16uYVgBagEnQlxCcS0m%2FdgdD4XlLENTMgqdi3F%2BcK43%2BNj6gir6OpubzlE%2Btn8ccno5%2BYhMf2wUr4TNMCDL6E%2FF4qZjMadXd4RQ6yz7Oc4KXPr6MN6dHUOuA%3D%3D&X-Amz-Signature=6b7d31cf1956a69edc2d7ba0fb8b698334333f0bfa4766909e0db7d856729962&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22KakaoTalk_20190720_010602920.jpg%22"
    }
  })
  }
</script>