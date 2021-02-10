<template>
  <div class="card-list">
    <card
      v-for="(monster, index) in monsters"
      :monster="monster"
      :key="index"
    ></card>
  </div>
</template>

<script>
  import Card from './Card.vue';

  export default {
    props: ['monsters'],
    components: {
      Card,
    },
  };
</script>

<style lang="scss" scoped>
  .card-list {
    width: max-content;
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 20px;
    justify-items: center;
    overflow: hidden;

    @media (max-width: 1300px) {
      grid-template-columns: repeat(3, 1fr);
    }

    @media (max-width: 992px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media (max-width: 700px) {
      grid-template-columns: repeat(1, 1fr);
    }
  }
</style>
