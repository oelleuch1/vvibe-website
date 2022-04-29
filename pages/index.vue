<template>
  <div class="home-page">
    <main-content></main-content>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import MainContent from "@/components/home/MainContent.vue";

export default Vue.extend({
  name: "HomeView",
  components: { MainContent },
});
</script>

<style lang="scss" scoped>
</style>