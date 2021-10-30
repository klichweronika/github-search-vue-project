<template>
  <Search @search="handleSearch" />
  <user :user="user" v-if="user" />
</template>

<script>
import Search from "./components/Search.vue";
import User from "./components/User.vue";

export default {
  name: "App",
  components: {
    Search,
    User,
  },

  data() {
    return {
      user: null,
    };
  },
  methods: {
    async handleSearch(value) {
      try {
        const response = await fetch(`https://api.github.com/users/${value}`);
        this.user = await response.json();
      } catch (err) {
        console.log(err);
      }
    },
  },
  async mounted() {
    try {
      const response = await fetch("https://api.github.com/users/octocat");
      this.user = await response.json();
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  font-size: 1.6rem;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;
  position: relative;
}

html {
  font-size: 70%;
}

#app {
  width: 50%;
}
</style>
