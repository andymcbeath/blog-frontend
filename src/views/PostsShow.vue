<script>
import axios from "axios";

export default {
  data: function () {
    return { posts: {},
    };
  },
  created: function()
  axios.get("/posts/2.json").then((response) => {
    this.recipe = response.data;
  },
};
</script>

<template>
  <div class="recipes-show">
    <div class="container">
      <h1>{{ posts.title }}</h1>
      <p>{{ posts.body }}</p>
      <p>{{ posts.title }}</p>
      <p>{{ posts.title }}</p>
    </div>
  </div>
</template>
