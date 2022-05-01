<template>
  <div class="home-page">
    <main-content />
    <conversations-that-converts />
    <celebrities />
    <signup-steps />
    <powerfull-tools />
    <line-with-svg direction="down" />
    <famous-people />
    <line-with-svg :with-circle="false" svg-id="medal" class="medal" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import MainContent from '@/components/home/MainContent.vue'
import ConversationsThatConverts from '~/components/home/ConversationsThatConverts.vue'
import Celebrities from '~/components/home/Celebrities.vue'
import SignupSteps from '~/components/home/SignupSteps.vue'
import PowerfullTools from '~/components/home/PowerfullTools.vue'
import LineWithSvg from '~/components/ui/molecules/LineWithSvg.vue'
import FamousPeople from '~/components/home/FamousPeople.vue'

export default Vue.extend({
  name: 'HomeView',
  components: {
    MainContent,
    ConversationsThatConverts,
    Celebrities,
    SignupSteps,
    PowerfullTools,
    LineWithSvg,
    FamousPeople,
  },
})
</script>

<style lang="scss" scoped>
.home-page {
  .medal {
    margin-bottom: 114px;
    ::v-deep .svg {
      left: -47%;
      top: 55px;
    }
  }
}
</style>