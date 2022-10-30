<template>
  <header class="header-box">
    <div class="header-panel-box">
      <div class="logo-box"></div>
      <router-link
        class="router-link-button"
        to="/randomanime"
        @click="showRandomAnime()"
        ><my-button-vue text="Random Anime"
      /></router-link>

      <router-link class="router-link-button" to="/"
        ><my-button-vue text="Go to Home"
      /></router-link>
      <!-- <router-link class="router-link-button" to="/favourite"
        ><my-button-vue text="Favourite" -->
      <!-- /></router-link> -->

      <div>
        <input
          type="search"
          class="my-search-input"
          placeholder="Search anime"
          v-model="searchInfo"
        />

        <my-button-vue text="Search" @click="showSearchAnime()"></my-button-vue>
      </div>
    </div>

    <!-- route outlet -->
    <!-- component matched by the route will render here -->
    <h1 class="header-title">MY ANIME</h1>
  </header>
  <!-- <router-view></router-view> -->
</template>

<script>
import MyButtonVue from "@/ui/MyButton.vue";
//    import axios from 'axios';

export default {
  name: "Header",
  components: {
    MyButtonVue,
  },
  data() {
    return {
      searchInfo: "",
    };
  },
  methods: {
    showSearchAnime() {
      this.$store.dispatch("fetchAnimeList", this.searchInfo);

      this.$router.push({
        name: "search",
        params: { titule: this.searchInfo },
      });
      return console.log(this.searchInfo);
    },
    showRandomAnime() {
      this.$store.dispatch("fetchRandomAnime");
    },
    onAnimeDetail(itemId) {
      this.$router.push({
        name: "anime",
        params: { id: itemId },
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/components/Header.scss";
</style>
