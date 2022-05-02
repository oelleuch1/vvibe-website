<template>
  <div class="button-with-border">
    <base-button :label="label"></base-button>
    <base-button class="border"></base-button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseButton from '@/components/ui/atoms/BaseButton.vue'

export default Vue.extend({
  name: 'ButtonWithBorder',
  components: { BaseButton },
  props: {
    label: String,
  },
})
</script>

<style lang="scss" scoped>
.button-with-border {
  position: relative;

  .border {
    border: $black--light 2px dashed;
    position: absolute;
    top: 11px;
    background: transparent;
    left: 8px;
  }
}
</style>