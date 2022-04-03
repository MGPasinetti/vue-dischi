<template>
  <div id="app">
    <header-dischi
      :options="arrOptions"
      @genre-selected="setGenreSelection"
      @author-inserted="setAuthorSearch"
    />
    <main-dischi
      :str-selected-genre="strGenre"
      :str-search-author="strAuthor"
      @data-fetched="setArrData"
    />
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
  data() {
    return {
      strGenre: '',
      strAuthor: '',
      arrDischi: [],
    };
  },
  computed: {
    arrOptions() {
      return [...new Set(this.arrDischi.map((element) => element.genre))];
    },
  },
  methods: {
    setArrData(arrDischiPassed) {
      this.arrDischi = arrDischiPassed;
    },
    setGenreSelection(genrePassed) {
      this.strGenre = genrePassed;
    },
    setAuthorSearch(authorPassed) {
      this.strAuthor = authorPassed;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
</style>
