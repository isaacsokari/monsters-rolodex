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

<style scoped>
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
    width: 100%;
  }

  .card-container:hover {
    transform: scale(1.05);
  }
</style>
