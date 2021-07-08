<template>
  <div id="app">
    <Header/>
    <Album/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Album from './components/Album.vue';

export default {
  name: 'App',
  components: {
    Header,
    Album
  }
}
</script>

<style lang="scss">
@import '@/style/global.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
