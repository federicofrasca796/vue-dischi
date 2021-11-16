<template>
  <div id="site_main">
    <div class="container">
      <SelectEl @filter-genre="selectGenre" />

      <div class="row" v-if="!loader">
        <SongCard
          v-for="poster in filterGenre"
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
import SelectEl from "../components/SelectEl.vue";

import axios from "axios";

export default {
  components: {
    SongCard,
    SelectEl,
  },
  data() {
    return {
      posters: [],
      loader: true,
      optionValue: "",
    };
  },

  mounted() {
    this.CallApi();
  },

  methods: {
    CallApi() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((resp) => {
          this.posters = resp.data.response;
          setTimeout(this.SeeLoading, 1000);
        })
        .catch((err) => {
          console.error(err, "ERROR");
        });
    },

    SeeLoading() {
      this.loader = false;
    },

    selectGenre(optionValue) {
      this.optionValue = optionValue;
    },
  },

  computed: {
    filterGenre() {
      const filteredArr = this.posters.filter((poster) => {
        return poster.genre.includes(this.optionValue);
      });
      return filteredArr;
    },
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