<template>
  <div id="site_header">
    <img
      src="../assets/Spotify_logo_without_text.svg"
      alt="spotify logo"
      height="60%"
    />

    <SelectEl />
  </div>
</template>

<script>
import SelectEl from "../components/SelectEl.vue";

export default {
  components: {
    SelectEl,
  },
};
</script>

<style lang='scss'>
#site_header {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  height: 80px;
  background: #2e3a46;
}
</style> 