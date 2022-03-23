<template>
  <body id="app">

    <FableHeader />
    <!-- hamburger menu -->
    <BurgerMenu />

  </body>
</template>

<script>
import FableHeader from './components/macro/FableHeader.vue'
import BurgerMenu from './components/commons/BurgerMenu.vue'

export default {
  name: 'App',
  components: {
    FableHeader,
    BurgerMenu
  }
}
</script>

<style lang="scss">
@import './assets/scss/_common.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  background-color: #4a6e9f;
  min-height: 100vh;
}
</style>
