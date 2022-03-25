<template>
  <div id="app">
    <header-dischi />
    <main-dischi />
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

<style lang="scss">
$primary: rgb(46,58,70);
$secondary: rgb(30,45,59);
@import "~bootstrap/scss/bootstrap";
</style>
