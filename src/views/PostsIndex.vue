<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Welcome to Andy's Great Posts",
      posts: [],
    };
  },
  created: function () {
    this.postsIndex();
  },
  methods: {
    postsIndex: function () {
      axios.get("/posts.json").then((response) => {
        this.posts = response.data;
        console.log("All Posts:", this.posts);
      });
    },
  },
};
</script>

<template>
  <div v-for="post in posts" v-bind:key="post.id">
    <h1>{{ post.title }}</h1>
    <img :src="post.image" alt="GREAT Posts" />
    <p>
      {{ post.body }}
    </p>
    <p>
      {{ post.image }}
    </p>
  </div>
</template>
