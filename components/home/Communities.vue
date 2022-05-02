<template>
  <div class="communities">
    <h2 class="communities__title">Communities of all kinds</h2>
    <div class="communities__description">
      From large retailers to small businesses, see how leading brands create
      value with Vvibe.
    </div>
    <div class="communities__logos">
      <base-image
        v-for="(logo, index) in logos"
        :key="index"
        :src="logo.url"
        :alt="logo.alt"
      />
    </div>

    <div class="communities__block">
      <block-with-styled-border :withCircle="false">
        <template #left-content>
          <div class="list">
            <block-with-color
              v-for="(people, index) in peoples"
              :key="index"
              :style="styles[index]"
              :class="{ image: people.image }"
              class="people"
            >
              <div
                v-if="people.name"
                v-text="people.name"
                class="people__name"
              ></div>
              <svg-icon
                v-if="people.svg"
                :id="people.svg"
                class="people__svg"
              ></svg-icon>
              <base-image
                v-if="people.image"
                :src="people.image"
                class="people__image"
              ></base-image>
            </block-with-color>
          </div>
        </template>

        <template #right-content>
          <div class="overview">
            <block-with-color>
              <div class="text">
                “Mit Vvibe haben wir eine Lösung geschaffen, die es möglich
                macht jede einzelne Nachricht am Spampostfach vorbei in den Kopf
                der Menschen zu bringen.”
              </div>
              <svg-icon id="logo-light" />
            </block-with-color>
          </div>
        </template>
      </block-with-styled-border>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
import SvgIcon from '../ui/atoms/SvgIcon.vue'
import BlockWithStyledBorder from '@/components/ui/organisms/BlockWithStyledBorder.vue'
import BlockWithColor from '@/components/ui/atoms/BlockWithColor.vue'

export default Vue.extend({
  components: { BaseImage, SvgIcon, BlockWithStyledBorder, BlockWithColor },
  name: 'Communities',
  data() {
    return {
      logos: [
        { url: '/img/intec-logo.svg', alt: 'intect logo' },
        { url: '/img/cargo-logo.svg', alt: 'cargo' },
        {
          url: '/img/entrepreneur-university-logo.svg',
          alt: 'entrepreneur university',
        },
        { url: '/img/cierra-logo.svg', alt: 'cierra' },
        { url: '/img/matthew-mockridge-logo.svg', alt: 'matthew mockridge' },
      ],

      peoples: [
        { image: '/img/robin-soder-communities.svg' },
        { name: 'Matthew Mockridge', svg: 'line-moved-right' },
        { image: '/img/matthew-mockridge-communities.svg' },
        { name: 'Robin Söder', svg: 'line-moved-up' },
        { name: null, svg: null, image: null },
        { image: '/img/vitto-emmermann-communities.svg' },
        { name: 'Vittorio Emmermann', svg: 'line-moved-left' },
      ],
      styles: [
        { width: '35%' },
        { width: 'calc(29% - 40px)', background: '#F2D19D', color: 'black' },
        { width: 'calc(36% - 3px)' },
        { width: 'calc(28% - 40px)', background: '#F2D19D', color: 'black' },
        { width: 'calc(7% - 1px)', padding: 0 },
        { width: '36%' },
        { width: 'calc(29% - 43px)' },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.communities {
  &__title {
    @include flex-center;
    font-family: 'Archivo Black';
    font-weight: bolder;
    font-size: 40px;
    line-height: 50px;
    text-align: left;
    text-transform: uppercase;
    margin: 0 auto;
  }

  &__description {
    font-family: 'Gilroy';
    font-size: 18px;
    line-height: 27px;
    text-align: center;
    letter-spacing: 0.01em;
    max-width: 400px;
    margin: 24px auto 44px auto;
    color: $purple--light;
  }

  &__logos {
    @include flex-justify-center;
    max-width: 820px;
    margin: 0 auto;

    img {
      height: 59px;
      width: 120px;
    }
  }

  &__block {
      @include full-width;
    height: 100%;
    margin-top: 145px;

    .overview {
      height: 100%;

      ::v-deep .block-with-color {
        padding: 102px 44px;
        height: calc(100% - 204px);
      }

      .text {
        font-family: 'Gilroy';
        font-style: normal;
        font-weight: 500;
        font-size: 30px;
        line-height: 50px;
        color: #fcf8f2;
        margin-bottom: 12px;
      }
    }

    .list {
      display: flex;
      flex-wrap: wrap;
      height: 100%;

      .people {
        border-right: 1px solid $black--light;
        &:not(.image) {
          padding: 24px 20px 0 20px;
          border-top: 1px solid $black--light;
        }

        &__name {
          font-family: 'Gilroy';
          font-weight: 600;
          font-size: 18px;
          line-height: 27px;
          text-transform: uppercase;
        }

        svg {
          position: relative;
          left: calc(100% - 80px);
          margin-top: 8px;
        }

        img {
          object-fit: cover;
          height: 100%;
          width: 100%;
        }
      }
    }
  }
}
</style>