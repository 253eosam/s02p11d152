<template>
  <v-layout py-4 h-100>
    <v-flex col>
      <h2 class="color-333 headline font-weight-light">{{title}}</h2>
      <div class="caption">{{formatedDate}}</div>
      <br />
      <p class="mb-1 color-666 font-weight-light subheading">{{body.substring(0,100)}}</p>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  name: "Post",
  props: {
    date: { type: Date },
    title: { type: String },
    body: { type: String }
  },
  computed: {
    formatedDate() {
      return `${this.date.getFullYear()}년 ${this.date.getMonth() +
        1}월 ${this.date.getDate()}일`;
    }
  }
};
</script>
<style>
.color-666 {
  color: #666;
}
.color-333 {
  color: #333;
}
.h-100 {
  height: 100%;
}
.caption {
  text-align: right;
}
</style>

