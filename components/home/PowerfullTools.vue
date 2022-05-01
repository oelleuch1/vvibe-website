<template>
  <div class="powerfull-tools">
    <h2 class="powerfull-tools__title">Powerful toolset and filtering</h2>
    <div class="powerfull-tools__description">
      Vvibe allows you to send messages directly to the people who want to hear
      from you. Our filtering lets you select demographics and user info in a
      variety of powerful combinations.
    </div>
    <base-image src="/img/powerfull-tools.svg" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
export default Vue.extend({
  components: { BaseImage },
  name: 'PowerfullTools',
})
</script>

<style lang="scss" scoped>
.powerfull-tools {
  margin: 124px 0;


  &__title {
    font-family: 'Archivo Black';
    font-style: normal;
    font-weight: bolder;
    font-size: 40px;
    line-height: 50px;
    text-transform: uppercase;
  }

  &__description {
    font-family: 'Gilroy';
    font-size: 18px;
    line-height: 28px;
    text-align: center;
    max-width: 650px;
    margin: 0 auto;
    margin-bottom: 44px;
  }

  img {
      width: 100%;
  }
}
</style>