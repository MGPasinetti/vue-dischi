<template>
    <div class="col">
        <div class="card shadow-sm">
            <img class="bd-placeholder-img card-img-top" src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="New Jersey">
            <div class="card-body">
                <h2 class="card-title">New Jersey</h2>
                <h3 class="card-text">Bon Jovi</h3>
                <h4 class="card-text">1988</h4>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DiscoCard',
  props: {
    discoData: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
