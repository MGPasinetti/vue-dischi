<template>
  <header class="bg-primary">
    <div class="d-flex justify-content-between align-items-center">
      <div class="column-left">
        <!-- spotify-logo -->
      </div>
      <div class="column-right align-self-center">
        <select class="p-1" name="generi" id="">
          <option value="all">--seleziona generi--</option>
          <option value="rock">rock</option>
          <option value="jazz">jazz</option>
          <option value="pop">pop</option>
          <option value="metal">metal</option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderDischi',
};
</script>

<style lang="scss" scoped>
header {
  height: 3.5rem;
}
</style>
