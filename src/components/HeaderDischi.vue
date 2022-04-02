<template>
  <header>
      <img src="../assets/img/spotify-logo.png" alt="spotify logo">
      <div class="searching-group">
          <select
            name="genreSelection"
            id="genreSelection"
            v-model="strGenre"
            @change="$emit('genre-selected', strGenre)"
          >
            <option value="Tutti i generi">
                Tutti i generi
            </option>
            <option
              v-for="option in arrOptions"
              :key="option"
              :value="option"
            >
                {{option}}
            </option>
          </select>
          <label for="author">
            <input
                type="text"
                v-model="strAuthor"
                placeholder="Cerca per autore"
                @input="$emit('author-inserted', strAuthor)"
            >
          </label>
          <button
            @click="reset"
          >
              Reset
          </button>
      </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
  props: {
    arrOptions: Array,
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
      this.$emit('genre-selected', this.strGenre);
      this.$emit('author-inserted', this.strAuthor);
    },
  },
};
</script>

<style lang="scss" scoped>
header {
    height: 4rem;
    background-color: #2E3A46;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;

    img {
        height: 3rem;
    }

    .searching-group > * {
        margin-left: 1rem;
    }
}
</style>
