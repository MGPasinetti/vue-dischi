<template>
  <div class="col text-center px-3 d-flex align-items-stretch" :id="albumData.genre">
      <div class="bg-primary p-3 mb-3 my-card">
        <img class="img-fluid" :src="albumData.poster" :alt="albumData.title">
        <h2 class="fs-5 mt-3 mb-4 text-white">{{ albumData.title.toUpperCase() }}</h2>
        <h3 class="fs-6 mb-0 my-color">{{ albumData.author }}</h3>
        <div class="mt-0 my-color">{{ albumData.year }}</div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'CardAlbum',
  props: {
    albumData: Object,
  },
};
</script>

<style lang="scss" scoped>
@import '../assets/style/style.scss';
.my-card{
  .my-color {
    color: grey;
  }
}
</style>
