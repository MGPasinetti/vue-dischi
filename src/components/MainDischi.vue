<template>
  <main class="py-5">
    <div class="container overflow-hidden">
      <div v-if="arrDischi === null">
        Dati in arrivo ...
      </div>
      <div
        v-else
        class="row row-cols-5 gx-5 gy-4"
      >
        <card-disco
          v-for="disco in arrFilteredDischi"
          :key="disco.title"
          :card="disco"
        />
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import CardDisco from './CardDisco.vue';

export default {
  name: 'MainDischi',
  components: {
    CardDisco,
  },
  props: {
    strSelectedGenre: String,
    strSearchAuthor: String,
  },
  data() {
    return {
      arrDischi: null,
    };
  },
  computed: {
    arrFilteredDischi() {
      if (this.strSelectedGenre === '') {
        return this.arrDischi.filter((disco) => disco.author.toLowerCase()
          .includes(this.strSearchAuthor.toLowerCase()));
      // eslint-disable-next-line no-else-return
      } else {
        return this.arrDischi.filter((disco) => disco.genre === this.strSelectedGenre
          && disco.author.toLowerCase().includes(this.strSearchAuthor.toLowerCase()));
      }
    },
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((axiosResponse) => {
        this.arrDischi = axiosResponse.data.response;
        this.$emit('data-fetched', this.arrDischi);
      });
  },
};
</script>

<style lang="scss" scoped>
main {
  min-height: calc(100vh - 66px);
  background-color: #1E2D3B;
}
</style>
