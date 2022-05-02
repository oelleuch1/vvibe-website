<template>
  <div class="latest-articles">
    <div class="latest-articles__title flex-justify-center">
      <h1 class="title">latest articles</h1>
      <nuxt-link to="/articles" class="link"> See all Posts </nuxt-link>
    </div>
    <div class="latest-articles__all flex-justify-center">
      <base-article
        v-for="(article, index) in articles"
        :key="index"
        :image-url="article.imageUrl"
        :title="article.title"
        :date="article.date"
        :description="article.description"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseArticle from '../ui/organisms/BaseArticle.vue'
export default Vue.extend({
  components: { BaseArticle },
  name: 'LatestArticles',
  data() {
    return {
      articles: [
        {
          imageUrl: '/img/phone.png',
          title: 'Vvibe Phone number',
          date: 'May 25, 2022',
          description:
            'Vvibe allows you to send messages directly to the people who want to hear from you. Our filtering lets you select...',
        },
        {
          imageUrl: '/img/app-messages.png',
          title: 'The app made for messages',
          date: 'May 25, 2022',
          description:
            'Vvibe allows you to send messages directly to the people who want to hear from you. Our filtering lets you select...',
        },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.latest-articles {
  margin: 112px 0;

  &__title {
    color: $black--light;
    text-align: left;
    margin-bottom: 40px;

    a.link {
      font-family: 'Gilroy';
      font-weight: 600;
      font-size: 16px;
      line-height: 24px;
      letter-spacing: 0.01em;
      text-transform: uppercase;
      color: $black--light;
      border-bottom: 1px dashed $black--light;
    }

    .title {
      font-family: 'Archivo Black';
      font-style: normal;
      font-weight: bolder;
      font-size: 40px;
      line-height: 50px;
      text-transform: uppercase;
    }
  }

  &__all {
    ::v-deep .article {
      width: 520px;
    }
  }
}
</style>