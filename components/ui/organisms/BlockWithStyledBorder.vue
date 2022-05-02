<template>
  <div class="block-with-styled-border">
    <line-with-svg :with-circle="withCircle"></line-with-svg>
    <div class="block-with-styled-border__content">
      <div class="left">
        <slot name="left-content"></slot>
      </div>
      <div class="right">
        <slot name="right-content"></slot>
      </div>
    </div>
    <line-with-svg class="line" :with-circle="false"></line-with-svg>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import LineWithSvg from '@/components/ui/molecules/LineWithSvg.vue'

export default Vue.extend({
  name: 'BlockWithStyledBorder',
  components: { LineWithSvg },
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
      width: calc(49% - 10px);
      border-right: 1px solid $black--light;
    }

    .right {
      width: calc(51% + 13px);
    }
  }

  .line {
    position: relative;
    top: -20px;
  }
}
</style>