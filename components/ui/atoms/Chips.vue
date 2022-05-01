<template>
  <div v-bind="$attrs" v-on="$listeners" class="chips">
    <div :class="{ underline }" class="chips__value">{{ label }}</div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Chips',
  props: {
    label: {
      type: String,
      required: true,
    },
    underline: {
        type: Boolean,
        default: false
    }
  },
})
</script>

<style lang="scss" scoped>
.chips {
  border: 2px solid $black--light;
  box-sizing: border-box;
  border-radius: 40px;
  padding: 15px 50px 17px 50px;
  height: 70px;

  &__value {
    font-weight: 600;
    font-size: 32px;
    text-align: center;

    &.underline {
      border-bottom: 2px solid $black--light;
    }
  }
}
</style>