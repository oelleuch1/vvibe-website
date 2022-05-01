<template>
  <div class="block-with-styled-border">
    <line-with-star :with-circle="withCircle"></line-with-star>
    <div class="block-with-styled-border__content">
      <div class="left">
        <slot name="left-content"></slot>
      </div>
      <div class="right">
        <slot name="right-content"></slot>
      </div>
    </div>
    <line-with-star class="line" :with-circle="false"></line-with-star>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import LineWithStar from '@/components/ui/molecules/LineWithStar.vue'

export default Vue.extend({
  name: 'BlockWithStyledBorder',
  components: { LineWithStar },
  props: {
    withCircle: {
      type: Boolean,
      default: true,
    },
  },
})
</script>

<style lang="scss" scoped>
.block-with-styled-border {
  position: relative;
  &__content {
    display: flex;
    justify-content: space-between;
    width: 100%;

    .left {
      width: calc(48% + 2px);
      border-right: 1px solid $black--light;
    }

    .right {
      width: 52%;
    }
  }

  .line {
    position: relative;
    top: -20px;
  }
}
</style>