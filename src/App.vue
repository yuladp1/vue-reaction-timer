<template>
  <h1>Reaction timer</h1>
  <h2 v-if="!isPlaying">Tap the button below</h2>
  <button @click="start" v-bind:disabled="isPlaying">Play!</button>
  <Block v-if="isPlaying" v-bind:delay="delay" @end="endGame"  ></Block>
  <Resulttab v-if="showResults" v-bind:score="score" />
  </template>

<script>
import Block from './components/Block-tab.vue'
import Resulttab from './components/result--tab.vue'
export default {
  name: 'App',
  components: {Block, Resulttab},
  data() {
     return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false

    }
  },
  methods: {
    start() {
      this.delay = 2000+ Math.random()*5000,
      this.isPlaying = true,
      this.showResults = false,
      console.log(this.delay)
    },
    endGame(result) {
      this.score = result,
      this.isPlaying = false,
      this.showResults = true

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button:disabled {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
