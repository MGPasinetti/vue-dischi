<template>
    <div class="card col">
        <img :src="dataDisco.poster" :alt="dataDisco.title">
        <h1>{{dataDisco.title.toUpperCase()}}</h1>
        <h2>{{dataDisco.author}}</h2>
        <h3>{{dataDisco.year}}</h3>
    </div>
</template>

<script>
export default {
  name: 'CardDisco',
  props: {
    dataDisco: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
