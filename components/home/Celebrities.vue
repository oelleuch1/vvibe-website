<template>
  <div class="celebrities">
    <div class="celebrities__content">
      <list-chips :items="celebrities" class="list-chips" />
      <div class="title">
        We help celebrities to create meaningfull connections
      </div>
      <div class="subtitle">
        <svg-icon id="line" />
        <div class="text">Sam Smith, celebrity</div>
        <svg-icon id="arrow-here" />
      </div>
      <div class="description">
        “Vvibe is a subscription platform that gives brands the tools they need
        to connect directly with their audiences without all the algorithms.”
      </div>
      <button-with-border label="I want it" />
    </div>
    <div class="celebrities__image">
      <base-image src="/img/celebrities.png" class="image" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
import SvgIcon from '../ui/atoms/SvgIcon.vue'
import ButtonWithBorder from '../ui/molecules/ButtonWithBorder.vue'
import ListChips from '../ui/molecules/ListChips.vue'

export default Vue.extend({
  components: { ListChips, SvgIcon, ButtonWithBorder, BaseImage },
  name: 'Celebrities',
  data() {
    return {
      celebrities: [
        { label: 'Celebrities' },
        { label: 'Actors' },
        { label: 'Musicians' },
        { label: 'Sportsmen' },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.celebrities {
  margin: 157px 30px;
  display: flex;
  justify-content: space-between;

  &__content {
    flex: 45% 0 0;

    .list-chips {
      margin-bottom: 56px;
    }

    .title {
      font-family: 'Archivo Black';
      font-weight: bolder;
      font-size: 28px;
      line-height: 150%;
      text-align: left;
      text-transform: uppercase;
      color: $black--light;
    }

    .subtitle {
      @include flex-center;
      margin-top: 41px;
      margin-bottom: 12px;
      width: 255px;

      svg {
        &:first-child {
          margin-right: 8px;
        }
        &:last-child {
          position: relative;
          top: -10px;
        }
      }

      .text {
        font-family: 'Gilroy';
        font-weight: 600;
        font-size: 16px;
        line-height: 24px;
        letter-spacing: 0.01em;
        text-transform: uppercase;
      }
    }

    .description {
      font-family: 'Gilroy';
      font-weight: 400;
      font-size: 18px;
      line-height: 28px;
      letter-spacing: 0.01em;
      color: $purple--light;
      margin-bottom: 48px;
      text-align: left;
    }
  }

  &__image {
    .image {
      width: 510px;
      height: 428px;
    }
  }

  ::v-deep .chips {
    padding: 12px 24px;
    width: 120px;
    height: 40px;

    &:first-child {
      color: $white;
      background: $primary;
    }

    &__value {
      font-weight: 600;
      font-size: 14px;
    }
  }
}
</style>

