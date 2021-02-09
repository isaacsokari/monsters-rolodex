<template>
  <div className="App">
    <h1>Monsters Rolodex</h1>

    <search-box
      placeholder="Search Monsters by Name"
      v-model="filter"
    ></search-box>

    <h3 v-show="filter.length > 0" style="color: white; margin: 3rem;">
      Search term: "{{ filter }}".
    </h3>

    <CardList :monsters="filteredMonsters" />
  </div>
</template>

<script>
  import SearchBox from './components/SearchBox.vue';
  import CardList from './components/CardList.vue';
  export default {
    data() {
      return {
        monsters: [],
        filter: '',
      };
    },
    computed: {
      filteredMonsters() {
        return this.monsters.filter((monster) =>
          monster.name.toLowerCase().includes(this.filter.toLowerCase())
        );
      },
    },
    components: { SearchBox, CardList },
    mounted() {
      fetch('https://jsonplaceholder.typicode.com/users')
        .then((res) => res.json())
        .then((data) => (this.monsters = data));
    },
  };
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto',
      'Oxygen', 'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans',
      'Helvetica Neue', sans-serif;
    box-sizing: border-box;
    max-width: 100%;
  }
  body {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: linear-gradient(
      to left,
      rgba(7, 27, 82, 1) 0%,
      rgb(172, 91, 138) 100%
    );
  }

  code {
    font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
      monospace;
  }

  body {
    padding: 30px 0;
  }

  .App {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  h1 {
    font-family: 'Bigelow Rules';
    font-size: 72px;
    color: #0ccac4;
  }
</style>
