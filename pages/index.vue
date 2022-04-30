<template>
  <div class="home-page">
    <main-content />
    <conversations-that-converts />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import MainContent from "@/components/home/MainContent.vue";
import ConversationsThatConverts from "~/components/home/ConversationsThatConverts.vue";

export default Vue.extend({
  name: "HomeView",
  components: { MainContent, ConversationsThatConverts },
});
</script>

<style lang="scss" scoped>
</style>