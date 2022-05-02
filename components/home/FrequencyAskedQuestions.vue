<template>
  <div class="faq">
    <div class="flex-justify-center full-width">
      <div class="faq__content">
        <svg-icon id="speaker"></svg-icon>
        <h2 class="title">Frequently asked questions</h2>
        <button-with-border
          label="I want it"
          class="button"
        ></button-with-border>
      </div>

      <div class="faq__questions">
        <div v-for="(faq, index) in faqs" :key="index" class="link">
          <nuxt-link :to="`faq/${faq.slug}`" class="flex-justify-center">
            <h4 v-text="faq.question" class="link__title"></h4>
            <svg-icon id="go-to-link"></svg-icon>
          </nuxt-link>
        </div>
      </div>
    </div>
    <base-image src="/img/feature-is-existing.svg" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseImage from '../ui/atoms/BaseImage.vue'
import SvgIcon from '../ui/atoms/SvgIcon.vue'
import ButtonWithBorder from '@/components/ui/molecules/ButtonWithBorder.vue'

export default Vue.extend({
  name: 'FrequencyAskedQuestions',
  components: { SvgIcon, BaseImage, ButtonWithBorder },
  data() {
    return {
      faqs: [
        { question: 'How does Vvibe work?', slug: 'how-does-vvibe-work' },
        {
          question: 'Where is Vvibe currently available?',
          slug: 'where-is-vvibe-currently-available',
        },
        {
          question: 'Do I get a Vvibe Phone number?',
          slug: 'do-i-get-a-vvibe-phone-number',
        },
        {
          question: 'Is the app available to download in the app store?',
          slug: 'is-the-app-available-to-download-in-the-app-store',
        },
      ],
    }
  },
})
</script>

<style lang="scss" scoped>
.faq {
  position: relative;
  top: -15px;

  &__content {
    padding: 120px 125px 160px 150px;
    width: calc(49% - 287px);
    border-right: 1px solid $black--light;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    svg {
      margin-bottom: 40px;
    }

    .title {
      font-family: 'Archivo Black';
      font-weight: bolder;
      font-size: 40px;
      line-height: 50px;
      text-transform: uppercase;
      color: $black--light;
      margin-bottom: 32px;
      max-width: 340px;
      text-align: left;
    }
  }

  &__questions {
    width: calc(50% - 25px);
    position: relative;
    left: -20px;
    padding-left: 50px;

    .link {
      max-width: 600px;
      margin-bottom: 24px;
      border-bottom: 1px solid $black--light;

      &__title {
        font-family: 'Gilroy';
        font-weight: 600;
        font-size: 22px;
        line-height: 27px;
        color: $black--light;
        text-align: left;
        margin: 0;
        padding-bottom: 24px;
      }
    }
  }

  img {
    width: 618px;
    cursor: pointer;
  }
}
</style>