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
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
export default Vue.extend({
  components: { BaseImage },
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
}
</style>