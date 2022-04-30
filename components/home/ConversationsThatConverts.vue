<template>
  <div class="conversations-that-converts">
    <block-with-styled-border>
      <template #left-content>
        <div class="left-content">
          <h2 class="left-content__title">Conversations that convert</h2>
          <chips class="left-content__solution" label="solution"></chips>
          <div class="left-content__icons">
            <svg-icon id="pause"></svg-icon>
            <svg-icon id="play"></svg-icon>
            <base-image src="/img/author-3.png" class="image"></base-image>
          </div>
          <div class="left-content__icons">
            <chips label="get it" class="chip"></chips>
            <svg-icon id="next-arrow"></svg-icon>
          </div>
        </div>
      </template>

      <template #right-content>
        <div class="right-content">
          <paragraph-with-star
            v-for="(topic, index) in topics"
            :key="index"
            :label="topic.label"
            :description="topic.description"
            class="paragraph"
          />
        </div>
      </template>
    </block-with-styled-border>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BlockWithStyledBorder from '../ui/organisms/BlockWithStyledBorder.vue'
import Chips from '../ui/atoms/Chips.vue'
import SvgIcon from '../ui/atoms/SvgIcon.vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
import ParagraphWithStar from '../ui/molecules/ParagraphWithStar.vue'

export default Vue.extend({
  name: 'ConversationsThatConverts',
  components: {
    BlockWithStyledBorder,
    Chips,
    SvgIcon,
    BaseImage,
    ParagraphWithStar,
  },
  data() {
    return {
      topics: [
        {
          label: 'Grow your audience',
          description:
            'Vvibe is a subscription platform that gives brands the tools they need to connect directly with their audiences without all the algorithms.',
        },
        {
          label: 'Foster your community',
          description:
            'Vvibe is a subscription platform that gives brands the need to connect directly with their audiences without all the algorithms, spam, and noise getting in the way.',
        },
        {
          label: 'Earn an audience online',
          description:
            'Vvibe is a subscription platform that gives brands the they need to connect directly with their audiences without all the algorithms, spam, and noise getting.',
        },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.conversations-that-converts {
  .left-content {
    margin: 137px 52px 210px 82px;

    &__title {
      font-family: 'Archivo Black';
      font-weight: bolder;
      font-size: 60px;
      max-width: 380px;
      line-height: 50px;
      text-align: left;
      margin-bottom: 56px;
    }

    &__solution {
      margin-bottom: 24px;
    }

    &__icons {
      @include flex-justify-center;
      margin-bottom: 24px;

      .image {
        height: 70px;
        width: 70px;
      }

      .chip {
        width: calc(100% - 90px);
      }
    }
  }

  .right-content {
    padding: 137px 108px;

    .paragraph {
        margin-bottom: 44px;

        &:last-child {
            margin-bottom: 0;
        }
    }
  }
}
</style>