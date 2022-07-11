<template>
  <div class="dropdown_row">
    <label for="genres">Filtra per genere musicale</label>
    <select name="genres" id="genres">
      <option
        v-for="(element, index) in genreArray"
        :key="index"
        :value="element"
      >
        {{ element }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'DiscFilters',
  props: ['genreArray'],
};
</script>

<style lang="scss" scoped>
.dropdown_row {
  background-color: aquamarine;
  width: 100%;
  padding-block: 10px;
}
</style>
