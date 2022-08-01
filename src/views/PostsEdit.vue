<script>
import axios from "axios";
export default {
  data: function () {
    return {
      editPostParams: {},
      errors: [],
    };
  },
  created: function () {
    axios.get("/posts/" + this.$route.params.id + ".json").then((response) => {
      this.editPostParams = response.data;
    });
  },
  methods: {
    updatePost: function () {
      axios
        .patch("/posts/" + this.$route.params.id + ".json", this.editPostParams)
        .then((response) => {
          console.log(response.data);
          // this.editRecipeParams = response.data;
          this.$router.push("/posts");
        })
        .catch((error) => {
          this.errors = error.response.data.errors;
        });
    },
  },
};
</script>

<template>
  <div class="posts-edit">
    <form v-on:submit.prevent="updatePosts()">
      <h1>Update Posts</h1>
      <ul>
        <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
      </ul>
      <p>
        Title:
        <input type="text" v-model="editPostParams.title" />
      </p>
      <p>
        Body:
        <input type="text" v-model="editPostParams.body" />
      </p>
      <p>
        Image:
        <input type="text" v-model="editPostParams.image" />
      </p>
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
