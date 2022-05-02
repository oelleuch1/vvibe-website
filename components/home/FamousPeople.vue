<template>
  <div class="famous-people">
    <div class="famous-people__header flex-justify-center">
      <h2 class="title">
        <span> More than </span>
        <span class="highlighted"> 400,000 <svg-icon id="arrow-here" /> </span>
        <span class="famous"> famous </span>
        <span> people reached our users </span>
      </h2>
      <button-with-border label="I want it" class="button" />
    </div>

    <div class="famous-people__description">
      You favourite creators use Vvibe to connect with their audience through
      quick and convenient messages.
    </div>

    <div class="famous-people__all flex-justify-center full-width">
      <div v-for="(people, index) in peoples" :key="index" class="people">
        <base-image :src="people.imageUrl" :alt="people.name" />
        <div class="people__name" v-text="people.name"></div>
        <div class="people__fucntion" v-text="people.function"></div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
import SvgIcon from '../ui/atoms/SvgIcon.vue'
import ButtonWithBorder from '../ui/molecules/ButtonWithBorder.vue'
export default Vue.extend({
  components: { SvgIcon, ButtonWithBorder, BaseImage },
  name: 'FamousPeople',
  data() {
    return {
      peoples: [
        {
          name: 'sam smith',
          function: 'Celebrity',
          imageUrl: '/img/famous/sam-smith-f1.svg',
        },
        {
          name: 'matthew mockridge',
          function: 'Celebrity',
          imageUrl: '/img/famous/matthew-mockridge.svg',
        },
        {
          name: 'sam smith',
          function: 'Celebrity',
          imageUrl: '/img/famous/sam-smith-f2.svg',
        },
        {
          name: 'sam smith',
          function: 'Celebrity',
          imageUrl: '/img/famous/sam-smith-f3.svg',
        },
        {
          name: 'vitto emmermann',
          function: 'Celebrity',
          imageUrl: '/img/famous/vitto-emmermann.svg',
        },

        {
          name: 'Robin Söder',
          function: 'Celebrity',
          imageUrl: '/img/famous/robin-soder.svg',
        },
        {
          name: 'sam smith',
          function: 'Celebrity',
          imageUrl: '/img/famous/sam-smith-f4.svg',
        },
        {
          name: 'sam smith',
          function: 'Celebrity',
          imageUrl: '/img/famous/sam-smith-f5.svg',
        },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.famous-people {
  margin-bottom: 148px;
  &__header {
    margin-left: 40px;

    .title {
      font-family: 'Archivo Black';
      font-weight: bolder;
      font-size: 40px;
      line-height: 50px;
      text-transform: uppercase;
      max-width: 660px;
      text-align: left;

      .highlighted {
        color: #597dff;

        svg {
          position: relative;
          top: -30px;
          left: -12px;
        }
      }

      .famous {
        position: relative;
        left: -23px;
      }
    }

    .button {
      left: -75px;
    }
  }

  &__description {
    font-family: 'Gilroy';
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 28px;
    color: $purple--light;
    text-align: left;
    max-width: 550px;
    margin-left: 40px;
    margin-bottom: 112px;
  }

  &__all {

    .people {
      img {
        width: 130px;
        height: 130px;
        margin-bottom: 20px;
      }

      &__name {
        font-weight: 600;
        font-size: 16px;
        text-transform: uppercase;
        margin-bottom: 4px;
      }

      &__function {
        font-family: 'Gilroy';
        font-size: 16px;
        line-height: 28px;
        color: $purple--light;
      }
    }
  }
}
</style>