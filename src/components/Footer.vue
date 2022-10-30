<template>
  <footer class="header-box">
    <div class="header-panel-box">
      <div class="logo-box"></div>
      <router-link class="router-link-button" to="/randomanime"
        ><my-button-vue text="Random Anime"
      /></router-link>

      <router-link class="router-link-button" to="/"
        ><my-button-vue text="Go to Home"
      /></router-link>
      <!-- <router-link class="router-link-button" to="/favourite"
          ><my-button-vue text="Favourite"
        /></router-link> -->
      <form action="https://github.com/tiastaa/anime" class="git">
        <button>
          <img
            src="https://pbs.twimg.com/profile_images/1176197551453687808/CTlnrRea_400x400.jpg"
            alt=""
          />
        </button>
      </form>
    </div>
  </footer>
</template>

<script>
import MyButtonVue from "@/ui/MyButton.vue";
//    import axios from 'axios';

export default {
  name: "Footer",
  components: {
    MyButtonVue,
  },
  methods: {
    // data() {
    //     return {
    //         info: null
    //             };
    //         },
    // mounted() {
    //         axios
    //         .get('https://api.jikan.moe/v4/random/anime')
    //         .then(response => (this.info = response));
    //     },
    // data(){
    //     return{info:null}
    // },
    // mounted(){axios.get('https://api.jikan.moe/v4/random/anime')
    //     .then((resp)=>{
    //     this.info=resp.data.data;
    //     console.log(resp.data.data)
    // }),
    // ShowRandomAnime() {
    //   this.$router.push({
    //     name: 'randomanime',
    //   })}
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/components/Footer.scss";
</style>
