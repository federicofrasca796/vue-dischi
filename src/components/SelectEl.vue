<template>
  <select
    name="genre_filter"
    v-model="optionValue"
    @change="$emit('filter-genre', optionValue)"
  >
    <option selected></option>
    <option value="Rock">Rock</option>
    <option value="Pop">Pop</option>
    <option value="Jazz">Jazz</option>
    <option value="Metal">Metal</option>
  </select>
</template>

<script>
export default {
  data() {
    return {
      optionValue: "",
    };
  },
};
</script>

<style lang="scss">
select {
  margin-left: auto;
  font-size: 1.5rem;
  color: white;
  background: #2e3a46;
  padding: 0.8rem 2rem;
  border: none;
  border-radius: 5px;
}
</style>