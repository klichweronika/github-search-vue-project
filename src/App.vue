<template>
  <div class="app">
    <Search />
    <Profile />
  </div>
</template>

<script>
import Search from "./components/Search.vue";
import Profile from "./components/Profile.vue";

export default {
  components: {
    Search,
    Profile,
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
  height: 92.5vh;
  position: relative;
}

html {
  font-size: 62.5%;
}

.unavailable {
  color: #c3cddd !important;
}

@media (min-width: 768px) {
  .app {
    width: 85%;
    padding: 4rem;
  }
}

@media (min-width: 1440px) {
  .app {
    width: 750px;
  }
}
</style>
