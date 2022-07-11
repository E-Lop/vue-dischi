<template>
  <div class="dropdown_row">
    <label for="genres">Filtra per genere musicale</label>

    <select
      name="genres"
      id="genres"
      v-model="emittedValue"
      @change="$emit('filtering', emittedValue)"
    >
      <option value="all">All</option>
      <option
        v-for="(singleGenre, index) in info"
        :key="index"
        :value="singleGenre"
      >
        {{ singleGenre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'DiscFilters',
  data() {
    return {
      emittedValue: 'all',
    };
  },
  props: ['info'],
};
</script>

<style lang="scss" scoped>
.dropdown_row {
  background-color: aquamarine;
  width: 100%;
  padding-block: 10px;
}
</style>
