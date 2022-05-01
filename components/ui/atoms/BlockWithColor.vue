<template>
  <div v-bind="$attrs" v-on="$listeners" class="block-with-color">
      <slot></slot>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'BlockWithColor',
})
</script>

<style lang="scss" scoped>
.block-with-color {
    text-align: left;
    background: $primary;
    color: $white--light
}
</style>