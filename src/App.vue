<template>
  <div id="app">
    <Header />
    <Main /> 
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import "@fontsource/roboto";
import "@fontsource/roboto/700.css";

export default {
  name: 'App',
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
  @import './style/global.scss';

  #app {
    width: 100%;
    height: 100vh;
  }
</style>
