<template>
  <header class="d-flex justify-content-between p-2 px-3">
    <img
      src="../assets/img/spotify-logo.png"
      alt="Spotify logo"
      class="logo"
    >

    <div class="group-search d-flex align-items-center">
      <select
        id="genere"
        v-model="strGenre"
        name="genere"
        @change="$emit('genre-selected', strGenre)"
      >
        <option value="">
          Tutti i generi
        </option>
        <option
          v-for="option in options"
          :key="option"
          :value="option"
        >
          {{ option }}
        </option>
      </select>
      <label for="author">
        <input
          id="author"
          v-model="strAuthor"
          type="text"
          name="author"
          @input="$emit('author-inserted', strAuthor)"
        >
      </label>

      <button @click="reset">
        Reset
      </button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
  props: {
    options: Array,
  },
  data() {
    return {
      strGenre: '',
      strAuthor: '',
    };
  },
  methods: {
    reset() {
      this.strGenre = '';
      this.strAuthor = '';
      this.$emit('author-inserted', this.strAuthor);
      this.$emit('genre-selected', this.strGenre);
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  background-color: #2E3A46;
  .logo {
    height: 50px;
  }
  .group-search {
    gap: 1.5rem;
  }
}
</style>
