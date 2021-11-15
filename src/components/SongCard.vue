<template>
  <div class="col">
    <div class="song_card">
      <div class="song_thumb">
        <img src="https://picsum.photos/1000" alt="album cover" />
      </div>

      <div class="song_info">
        <h2 class="song_title">New Jersey</h2>
        <div class="song_author">Bon Jovi</div>
        <div class="song_date">1988</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang='scss'>
.col {
  width: calc(100% / 6);
  text-align: center;

  .song_card {
    background: #2e3a46;
    padding: 1rem;
    margin: 1rem 3rem;

    .song_thumb > img {
      width: 100%;
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