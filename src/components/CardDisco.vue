<template>
  <div class="col">
    <div class="card-disco p-3 h-100 text-white text-center">
      <img
        class="img-fluid"
        :src="card.poster"
        :alt="card.title"
      >
      <h2 class="fs-6 mt-3 mb-4">{{ card.title.toUpperCase() }}</h2>
      <h3 class="mb-0">{{ card.author }}</h3>
      <small class="mt-0">{{ card.year }}</small>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props: {
    card: Object,
  },
};
</script>

<style lang="scss" scoped>
.card-disco {
  background-color: #2E3A46;

  h3, small {
    color: grey;
    font-size: 16px;
  }

  small {
    font-size: 12px;
  }

  &:hover {
    background-color: #475868;
  }
}
</style>
