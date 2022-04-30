<template>
  <img
    v-bind="$attrs"
    v-on="$listeners"
    loading="lazy"
    class="base-image"
    :class="{ rounded: rounded }"
  />
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: "BaseImage",
    props: {
        rounded: Boolean
    }
})
</script>

<style lang="scss" scoped>
    .base-image {
        width: 60px;

        &.rounded {
            border-radius: 50%;
        }
    }
</style>

