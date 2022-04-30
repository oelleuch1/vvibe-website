<template>
  <div id="app">
    <div class="container">
      <main-header></main-header>
      <router-view />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import MainHeader from '@/components/header/MainHeader.vue'
export default Vue.extend({
  components: { MainHeader }
})
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $black;
  background: $primary-bg;
  padding: 0 40px;
  display: flex;
  flex-direction: column;
  align-items: center;

  .container {
    width: 100%;
    max-width: $md;
  }
}
</style>
