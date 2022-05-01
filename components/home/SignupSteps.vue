<template>
  <div class="signup-steps">
    <block-with-styled-border :withCircle="false">
      <template #left-content>
        <div class="signup-steps__overview">
          <block-with-color>
            <div class="title">Sign up in 5-ish minutes !</div>
            <div class="description">
              Lorem ipsum dolor sit amet, consectetur adipiscing. Aenean
              ultrices posuere senectus senectus. Non sagittis purus habitant
              iaculis.
            </div>
            <button-with-border label="uuu, sign me up" />
          </block-with-color>
        </div>
      </template>
      <template #right-content>
        <div class="signup-steps__list">
          <block-with-color
            v-for="(step, index) in steps"
            :key="index"
            class="step"
            :style="styles[index]"
          >
            <div v-text="step.number" class="step__number"></div>
            <div v-text="step.label" class="step__label"></div>
          </block-with-color>
        </div>
      </template>
    </block-with-styled-border>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BlockWithColor from '../ui/atoms/BlockWithColor.vue'
import ButtonWithBorder from '../ui/molecules/ButtonWithBorder.vue'
import BlockWithStyledBorder from '../ui/organisms/BlockWithStyledBorder.vue'
export default Vue.extend({
  components: { BlockWithStyledBorder, BlockWithColor, ButtonWithBorder },
  name: 'SignupSteps',
  data() {
    return {
      steps: [
        { number: 1, label: 'Create an account' },
        { number: 2, label: 'Get your phone number' },
        { number: 3, label: 'Connect with people' },
        { number: null, label: null },
        { number: null, label: null },
        { number: 4, label: 'Get a response' },
        { number: 5, label: 'Expand your community' },
        { number: null, label: null },
      ],
      styles: [
        { width: 'calc(29% - 40px)' },
        {
          width: 'calc(30% - 40px)',
          background: '#F2D19D',
          color: 'black',
        },
        { width: 'calc(31% - 40px)' },
        {
          width: 'calc(10% - 3px)',
          background: '#F2D19D',
          color: 'black',
          borderRight: 0,
          paddingRight: 0,
          paddingLeft: 0,
        },
        {
          width: '12%',
          background: '#F2D19D',
          color: 'black',
          borderBottom: 0,
          paddingRight: 0,
          paddingLeft: 0,
        },
        {
          width: 'calc(41% - 40px)',
          borderBottom: 0,
        },
        {
          width: 'calc(42% - 40px)',
          background: '#F2D19D',
          color: 'black',
          borderBottom: 0,
        },
        {
          width: 'calc(5% - 3px)',
          padding: '32px 0',
          borderRight: 0,
          borderBottom: 0,
          paddingRight: 0,
          paddingLeft: 0,
        },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.signup-steps {
  @include full-width;

  &__overview {
    height: 100%;

    ::v-deep .block-with-color {
      padding: 80px 80px 80px 124px;
    }

    .title {
      font-family: 'Archivo Black';
      font-weight: bolder;
      font-size: 40px;
      line-height: 50px;
      text-transform: uppercase;
      color: $white--light;
      margin-bottom: 24px;
    }

    .description {
      font-family: 'Gilroy';
      font-weight: 400;
      font-size: 18px;
      line-height: 28px;
      color: $white--light;
      max-width: 390px;
      text-align: left;
      margin-bottom: 40px;
    }

    ::v-deep .base-button {
      width: 192px;
      background: $white;
      color: $black;
      font-weight: 600;
      font-size: 16px;
    }

    ::v-deep .border {
      background: transparent;
      border-color: $white;
    }
  }

  &__list {
    display: flex;
    flex-wrap: wrap;
    height: 100%;

    .step {
      border-right: 1px solid $black;
      border-bottom: 1px solid $black;
      padding: 32px 20px 72px 20px;

      &__number {
        font-family: 'Archivo Black';
        font-weight: bolder;
        font-size: 40px;
        text-transform: uppercase;
        margin-bottom: 24px;
      }

      &__label {
        font-weight: 600;
        font-size: 18px;
        line-height: 27px;
      }
    }
  }
}
</style>