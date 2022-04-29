<template>
  <div class="main-content">
    <div class="main-content--sent">
      <svg-icon id="sent"></svg-icon>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import SvgIcon from "@/components/ui/atoms/SvgIcon.vue";
export default Vue.extend({
  name: "MainContent",
  components: { SvgIcon },
});
</script>

<style lang="scss" scoped>
</style>