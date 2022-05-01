<template>
  <div class="home-page">
    <main-content />
    <conversations-that-converts />
    <celebrities />
    <signup-steps />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import MainContent from "@/components/home/MainContent.vue";
import ConversationsThatConverts from "~/components/home/ConversationsThatConverts.vue";
import Celebrities from "~/components/home/Celebrities.vue";
import SignupSteps from "~/components/home/SignupSteps.vue";

export default Vue.extend({
  name: "HomeView",
  components: { MainContent, ConversationsThatConverts, Celebrities, SignupSteps },
});
</script>

<style lang="scss" scoped>
</style>