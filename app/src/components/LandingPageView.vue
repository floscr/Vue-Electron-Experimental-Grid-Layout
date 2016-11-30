<style scoped>
  .grid {
    width: 100%;
    height: 100%;
    background-color: #fff;
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-column-gap: 15px;
    grid-row-gap: 15px;
  }

  footer {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 20px;
    border-top: 1px solid grey;
    display: flex;
    background-color: white;
  }
</style>

<template>
  <div>

    <div class="grid">
      <div v-for="index in gridItems">
        {{ index }}
      </div>
    </div>

    <footer>
      <button @click="reduce">Reduce</button>
      <button @click="add">Add</button>
    </footer>

  </div>
</template>

<script>
import CurrentPage from './LandingPageView/CurrentPage'
import Links from './LandingPageView/Links'
import Versions from './LandingPageView/Versions'

export default {

  name: 'landing-page',

  data: () => ({
    gridItems: 100
  }),

  methods: {
    reduce () {
      this.gridItems--
    },
    add () {
      this.gridItems = this.gridItems + 10
    }
  },

  components: {
    CurrentPage,
    Links,
    Versions
  }

}
</script>
