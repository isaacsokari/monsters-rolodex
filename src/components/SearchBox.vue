<template>
  <input
    type="search"
    className="search"
    :placeholder="placeholder"
    :value="filter"
    @input="$emit('input', $event.target.value)"
  />
</template>

<script>
  export default {
    props: ['placeholder', 'filter'],
  };
</script>

<style scoped>
  .search {
    -webkit-appearance: none;
    border: 2px solid #ededed;
    border-radius: 10px;
    outline: none;
    padding: 0.5rem 1rem;
    width: 20rem;
    line-height: 2rem;
    margin: 2rem auto;
  }
</style>
