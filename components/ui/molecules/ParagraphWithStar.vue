star<template>
  <div v-bind="$attrs" v-on="$listeners" class="paragraph-with-star">
    <div class="paragraph-with-star__title">
      <svg-icon id="magic-star"></svg-icon>
      <div class="title-value" v-text="label"></div>
    </div>
    <div class="paragraph-with-star__description" v-text="description"></div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SvgIcon from '@/components/ui/atoms/SvgIcon.vue'

export default Vue.extend({
  name: 'ParagraphWithStar',
  components: { SvgIcon },
  props: {
    label: String,
    description: String,
  },
})
</script>

<style lang="scss" scoped>
.paragraph-with-star {
  &__title {
    display: flex;
    align-items: center;
    margin-bottom: 8px;

    .title-value {
      font-weight: 500;
      font-size: 30px;
      line-height: 40px;
      margin-left: 20px;
    }
  }

  &__description {
    font-family: 'Gilroy';
    font-size: 18px;
    line-height: 28px;
    color: $purple--light;
    max-width: 500px;
    text-align: left;
  }
}
</style>