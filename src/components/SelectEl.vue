<template>
  <select name="genre_filter">
    <option selected></option>
    <option value="Rock">Rock</option>
    <option value="Pop">Pop</option>
    <option value="Jazz">Jazz</option>
    <option value="Metal">Metal</option>
  </select>
</template>

<script>
export default {};
</script>

<style lang="scss">
select {
  margin-left: auto;
  font-size: 1.5rem;
  color: white;
  background: #1e2d3b;
  padding: 0.8rem 1.2rem;
  border: none;
  border-radius: 5px;
}
</style>