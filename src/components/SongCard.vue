<template>
  <div class="col">
    <div class="song_card">
      <div class="song_thumb">
        <img :src="imgSrc" alt="album cover" />
      </div>

      <div class="song_info">
        <h2 class="song_title">{{ songTitle }}</h2>
        <div class="song_author">{{ songAuthor }}</div>
        <div class="song_date">{{ songDate }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    songTitle: String,
    songAuthor: String,
    songDate: String,
    imgSrc: String,
  },
};
</script>

<style lang='scss'>
.col {
  width: calc(100% / 6);
  text-align: center;
  margin: 1rem 0;

  .song_card {
    background: #2e3a46;
    padding: 2rem 1rem;
    margin: 2rem;
    height: 100%;

    .song_thumb > img {
      width: 80%;
    }
    .song_info {
      padding: 1rem 0;
      .song_title {
        text-transform: uppercase;
        margin-bottom: 1rem;
      }
      .song_author,
      .song_date {
        font-size: 1.2rem;
        color: #5d6f7a;
      }
    }
  }
}
</style>