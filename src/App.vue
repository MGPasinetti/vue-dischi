<template>
  <div id="app">
    <HeaderDischi />
    <MainDischi />
  </div>
</template>

<script>
import HeaderDischi from './components/HeaderDischi.vue';
import MainDischi from './components/MainDischi.vue';

export default {
  name: 'App',
  components: {
    HeaderDischi,
    MainDischi,
  },
};
</script>

<style lang="scss" scoped>
@import "~bootstrap/scss/bootstrap";

#app {
  min-width: 1200px;
  padding: 0;
  margin: 0;
}
</style>
