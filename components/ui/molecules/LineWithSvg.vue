<template>
  <div
    v-bind="$attrs"
    v-on="$listeners"
    :class="{ down: direction === 'down' }"
    class="line-with-svg"
  >
    <svg-icon
      v-if="withCircle"
      id="half-circle-star"
      :class="{ down: direction === 'down' }"
      class="circle"
    ></svg-icon>
    <div v-else></div>
    <svg-icon
      class="svg"
      :id="svgId"
      fill="#121216"
    ></svg-icon>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SvgIcon from '@/components/ui/atoms/SvgIcon.vue'

export default Vue.extend({
  components: { SvgIcon },
  name: 'LineWithSvg',
  props: {
    withCircle: {
      type: Boolean,
      default: true,
    },
    direction: {
      type: String,
      default: 'up',
      validator(value) {
        return ['up', 'down'].includes(value)
      },
    },
    withStar: {
      type: Boolean,
      default: true,
    },
    svgId: {
      type: String,
      default: "magic-star"
    }
  },
})
</script>

<style lang="scss" scoped>
.line-with-svg {
  @include flex-justify-end;
  border-bottom: 1px solid $black--light;

  &.down {
    position: relative;
    top: -118px;
  }

  .circle {
    height: 119px;
    position: relative;
    bottom: -2px;
    left: calc(100% - 195px);
    z-index: 2;

    &.down {
      transform: rotate(180deg);
      bottom: -118px;
    }
  }

  .svg {
    left: -51%;
    position: relative;
    top: 11px;
  }
}
</style>