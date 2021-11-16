<template>
  <div id="site_main">
    <div class="container">
      <div class="row" v-if="!loader">
        <SongCard
          v-for="poster in posters"
          :key="poster.title"
          :imgSrc="poster.poster"
          :songTitle="poster.title"
          :songAuthor="poster.author"
          :songDate="poster.year"
        />
      </div>
      <div class="empty_bg" v-else>
        <h2>Loading...</h2>
      </div>
    </div>
  </div>
</template>

<script>
import SongCard from "./SongCard.vue";
import axios from "axios";

export default {
  components: {
    SongCard,
  },
  data() {
    return {
      posters: [],
      loader: true,
    };
  },

  methods: {
    SeeLoading() {
      this.loader = false;
    },
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        console.log(resp.data.response);
        this.posters = resp.data.response;
        setTimeout(this.SeeLoading, 3000);
      })
      .catch((err) => {
        console.error(err, "ERROR");
      });
  },
};
</script>

<style lang="scss">
#site_main,
.empty_bg {
  background: #1e2d3b;
  //   height: calc(100vh - 80px);
  height: calc(100vh - 80px);
  text-align: center;
  .container {
    padding: 5rem 1rem;
  }
  .row {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
}
</style>