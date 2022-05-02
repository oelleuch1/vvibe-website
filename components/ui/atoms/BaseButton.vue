<template>
  <button class="base-button flex-center" v-bind="$attrs" v-on="$listeners">
    {{ label }}
  </button>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'BaseButton',
  props: {
    label: String,
  },
})
</script>

<style lang="scss" scoped>
.base-button {
  width: 116px;
  height: 48px;
  background: $black--light;
  border-radius: 4px;
  color: $white;
  font-family: 'Gilroy';
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0.01em;
  text-transform: uppercase;
  border: 0;
}
</style>