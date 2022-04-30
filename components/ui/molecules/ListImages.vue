<template>
  <div v-bind="$attrs" v-on="$listeners" class="list-images">
    <base-image
      v-for="(image, index) in images"
      :key="index"
      :src="image"
      :style="{ left: `${getPositionIndexInGroup(index)}px` }"
      rounded
    ></base-image>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '@/components/ui/atoms/BaseImage.vue'

export default Vue.extend({
  components: { BaseImage },
  name: 'ListImages',
  props: {
    images: {
      type: Array,
      default() {
        return []
      },
    },
  },
  methods: {
    getPositionIndexInGroup(index: number): number {
      if (!index) return 0;
      return -index * 10;
    },
  },
})
</script>

<style lang="scss" scoped>
.list-images {
  ::v-deep .base-image {
    position: relative;
  }
}
</style>