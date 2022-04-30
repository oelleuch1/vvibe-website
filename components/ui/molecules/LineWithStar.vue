<template>
  <div v-bind="$attrs" v-on="$listeners" class="line-with-star">
    <svg-icon class="circle" v-if="withCircle" id="half-circle-star"></svg-icon>
    <div v-else></div>
    <svg-icon class="star" id="magic-star" fill="#121216"></svg-icon>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SvgIcon from '@/components/ui/atoms/SvgIcon.vue'

export default Vue.extend({
  components: { SvgIcon },
  name: 'LineWithStar',
  props: {
    withCircle: {
      type: Boolean,
      default: true,
    },
  },
})
</script>

<style lang="scss" scoped>
.line-with-star {
  @include flex-justify-end;
  border-bottom: 1px solid $black--light;

  .circle {
    height: 119px;
    position: relative;
    bottom: -2px;
    left: calc(100% - 195px);
    z-index: 2;
    background: $primary-bg;
  }

  .star {
    left: -55%;
    position: relative;
    top: 11px;
  }
}
</style>