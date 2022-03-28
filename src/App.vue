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
</style>
