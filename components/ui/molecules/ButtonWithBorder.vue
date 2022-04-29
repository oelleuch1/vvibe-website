<template>
  <div class="button-with-border">
    <base-button label="log in"></base-button>
    <base-button class="border"></base-button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import BaseButton from "@/components/ui/atoms/BaseButton.vue";

export default Vue.extend({
  name: "ButtonWithBorder",
  components: { BaseButton },
});
</script>

<style lang="scss" scoped>
.button-with-border {
  position: relative;

  .border {
    border: $black--light 2px dashed;
    position: absolute;
    background: $primary-bg;
    top: 11px;
    background: transparent;
    left: 8px;
  }
}
</style>