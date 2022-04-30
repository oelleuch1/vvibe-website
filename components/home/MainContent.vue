<template>
  <div class="main-content">
    <!-- <div class="main-content__sent">
      <svg-icon id="sent"></svg-icon>
    </div> -->
    <div class="main-content__block">
      <div class="sentense">Connect instantly</div>
      <div class="wrapper">
        <svg-icon id="comment-with-love"></svg-icon>
        <div class="sentense">with your</div>
        <list-images :images="images"></list-images>
      </div>
      <div class="sentense">audience in the</div>
      <div class="sentense indigo">most effective way</div>
    </div>
    <div class="main-content__footer">
      <div class="wrapper">
        <svg-icon id="location"></svg-icon>
        <svg-icon id="line-moved"></svg-icon>
      </div>
      <button-with-border class="button" label="I want it"></button-with-border>
      <svg-icon id="comment"></svg-icon>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SvgIcon from '@/components/ui/atoms/SvgIcon.vue'
import ListImages from '@/components/ui/molecules/ListImages.vue'
import ButtonWithBorder from '@/components/ui/molecules/ButtonWithBorder.vue'
export default Vue.extend({
  name: 'MainContent',
  components: { SvgIcon, ListImages, ButtonWithBorder },
  data() {
    return {
      images: ['/img/author-1.png', '/img/author-2.png', '/img/author-3.png'],
    }
  },
})
</script>

<style lang="scss" scoped>
.main-content {
  margin-top: 60px;

  &__block {
    width: 100%;

    .wrapper {
      display: flex;
      align-items: center;
      justify-content: center;

      .sentense {
        margin: 0 40px;
      }
    }

    .sentense {
      font-family: 'Archivo Black', sans-serif;
      font-size: 80px;
      text-align: center;
      letter-spacing: 0.005em;
      text-transform: uppercase;
      color: $black--light;
      font-weight: bolder;

      &.indigo {
        color: $primary;
      }
    }
  }

  &__footer {
    margin-top: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    .wrapper {
      margin-left: 75px;

      svg {
        &:first-child {
          margin-right: 24px;
        }
        &:last-child {
          position: relative;
          top: -42px;
        }
      }
    }

    .button {
      right: 100px;
    }

    svg {
      margin-right: 110px;
    }
  }
}
</style>