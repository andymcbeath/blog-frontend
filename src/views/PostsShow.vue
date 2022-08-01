<script>
import axios from "axios";

export default {
  data: function () {
    return {
      posts: {},
    };
  },
  created: function () {
    axios.get("/posts/2.json").then((response) => {
      this.post = response.data;
    });
  },
  methods: {},
};
</script>

<template>
  <div class="posts-show">
    <div class="container">
      <h1>{{ posts.title }}</h1>
      <p>{{ posts.body }}</p>
      <router-link to="/posts">Back to all Posts</router-link>
    </div>
  </div>
</template>
