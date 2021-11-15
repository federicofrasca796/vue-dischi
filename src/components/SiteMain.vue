<template>
  <div id="site_main">
    <div class="container">
      <div class="row">
        <SongCard />
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
      songs: [],
    };
  },

  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        console.log(resp.data);
      })
      .catch((err) => {
        console.error(err, "ERROR");
      });
  },
};
</script>

<style lang="scss">
#site_main {
  background: #1e2d3b;
  height: calc(100vh - 80px);
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