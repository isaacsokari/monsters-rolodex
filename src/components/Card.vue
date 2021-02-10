<template>
  <div className="card-container">
    <!-- :src="'https://robohash.org/' + monster.id + '?set=set2&size=180x180'" -->
    <img
      v-bind="{
        src: `https://robohash.org/${monster.id}?set=set2&size=180x180`,
      }"
      :alt="monster.name"
    />
    <h2>{{ monster.name }}</h2>
    <p>{{ monster.email }}</p>
  </div>
</template>

<script>
  export default {
    props: ['monster'],
  };
</script>

<style lang="scss" scoped>
  .card-container {
    display: flex;
    flex-direction: column;
    background-color: #95dada;
    border: 1px solid grey;
    border-radius: 5px;
    padding: 25px;
    cursor: pointer;
    -moz-osx-font-smoothing: grayscale;
    backface-visibility: hidden;
    transform: translateZ(0);
    transition: transform 0.25s ease-out;
    /* min-width: 280px; */
    /* width: 90%; */
    width: 280px;

    img {
      margin: 0 0 1rem;
    }
  }

  .card-container:hover {
    transform: scale(1.05);
  }
</style>
