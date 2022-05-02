<template>
  <div class="article">
    <base-image :src="imageUrl" class="article__image"></base-image>
    <div class="article__title flex-justify-center">
      <h3 class="title" v-text="title"></h3>
      <div class="date" v-text="date"></div>
    </div>
    <div class="article__description flex-justify-center">
      <div class="text" v-text="description"></div>
      <svg-icon id="outside-link"></svg-icon>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../atoms/BaseImage.vue'
import SvgIcon from '../atoms/SvgIcon.vue'
export default Vue.extend({
  components: { BaseImage, SvgIcon },
  name: 'BaseArticle',
  props: {
    imageUrl: String,
    title: String,
    description: String,
    date: String,
  },
})
</script>

<style lang="scss" scoped>
.article {
  font-family: 'Gilroy';

  &__image {
    width: 520px;
  }

  &__title {
    margin-top: 24px;
    padding-bottom: 24px;
    border-bottom: 1px solid $black--light;

    .title {
      font-weight: 500;
      font-size: 30px;
      line-height: 40px;
      text-align: left;
      margin: 0;
    }

    .date {
      font-style: normal;
      font-weight: 500;
      font-size: 18px;
      line-height: 28px;
      color: $purple--light;
    }
  }

  &__description {
    padding-bottom: 12px;
    border-bottom: 1px solid $black--light;

    .text {
      font-size: 18px;
      line-height: 28px;
      letter-spacing: 0.01em;
      color: $purple--light;
      margin-top: 12px;
      max-width: 450px;
      text-align: left;
    }
  }
}
</style>