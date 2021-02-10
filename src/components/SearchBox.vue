<template>
  <input
    type="search"
    className="search"
    :placeholder="placeholder"
    v-model="content"
  />
</template>

<script>
  export default {
    props: ['placeholder', 'value'],
    data() {
      return {
        content: this.$props.value,
      };
    },
  };
</script>

<style lang="scss" scoped>
  .search {
    -webkit-appearance: none;
    border: 2px solid #ededed;
    border-radius: 10px;
    outline: none;
    padding: 0.5rem 1rem;
    width: 20rem;
    line-height: 2rem;
    margin: 2rem auto;

    @media (max-width: 425px) {
      width: 280px;
    }
  }
</style>
