<template>
  <div id="app"></div>
</template>

<script>
import "./components/SiteHeader.vue";
import "./components/SiteMain.vue";

export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
  },
};
</script>

<style>
@import "../node_modules/bootstrap/scss/bootstrapp.scss";
</style>
