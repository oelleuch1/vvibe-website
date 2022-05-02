<template>
  <div class="menu flex-justify-center">
    <nuxt-link to="/" class="menu__logo flex-center">
      <svg-icon id="logo"></svg-icon>
    </nuxt-link>
    <div class="menu__items flex-justify-start">
      <nuxt-link
        v-for="item in items"
        :key="item.value"
        :to="item.url"
        class="item"
        :class="{ isActive: item.isSelected }"
      >
        <div v-text="item.value" class="value"></div>
        <svg-icon v-if="item.isSelected" id="magic-star"></svg-icon>
      </nuxt-link>
    </div>
    <nuxt-link to="/login" class="menu__login">
      <button-with-border label="Log in"></button-with-border>
    </nuxt-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import SvgIcon from '@/components/ui/atoms/SvgIcon.vue'
import ButtonWithBorder from '@/components/ui/molecules/ButtonWithBorder.vue'

export default Vue.extend({
  name: 'MainHeader',
  components: { SvgIcon, ButtonWithBorder },
  data() {
    return {
      items: [
        { value: 'About', url: '/about', isSelected: true },
        { value: 'How it works', url: '/how-it-works', isSelected: false },
        { value: 'Communities', url: '/communities', isSelected: false },
        { value: 'Blog', url: '/blog', isSelected: false },
      ],
    }
  },
  watch: {
    // "$route.path": {
    //   handler(value) {
    //     this.items = this.items.map(item => {
    //       item.isSelected = item.url === value
    //       return item
    //     })
    //   },
    //   immediate: true
    // }
  },
})
</script>

<style lang="scss" scoped>
.menu {
  height: 100px;
  border-bottom: $black--light solid 1px;

  &__logo {
    flex: 150px 0 0;
  }

  &__items {
    flex: 50% 0 0;
    height: 20px;

    .item {
      color: $black--light;
      font-family: 'Gilroy';
      font-weight: 500;
      font-size: 14px;
      line-height: 21px;
      letter-spacing: 0.01em;
      text-transform: uppercase;

      &:hover {
        color: $primary;
      }

      .value {
        margin-bottom: 6px;
      }
    }
  }

  &__login {
    flex: 150px 0 0;
  }
}
</style>