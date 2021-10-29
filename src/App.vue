<template>
  <div class="app">
    <SearchBar />
    <User />
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
import User from "./components/User";
import { provide } from "vue";
import store from "@/store";

export default {
  name: "App",
  components: {
    SearchBar,
    User,
  },
  setup() {
    provide("store", store);

    store.methods.searchUser();

    return { store };
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
