<template>
  <div class="list-chips">
    <chips
      v-for="(item, index) in items"
      :key="index"
      :label="item.label"
      :style="item.style"
      :underline="item.underline"
      class="chips"
    ></chips>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Chips from '@/components/ui/atoms/Chips.vue'
export default Vue.extend({
  components: { Chips },
  name: 'ListChips',
  props: {
      items: {
          type: Array,
          default() {
              return [];
          }
      }
  }
})
</script>

<style lang="scss" scoped>

.list-chips {
    @include flex-justify-center;

    .chips {
        margin-right: 16px;

        &:last-child {
            margin-right: 0;
        }
    }
}
</style>