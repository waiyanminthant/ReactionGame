<template>
  <h1>How fast can you catch me?</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <ClickBlock v-if="isPlaying" :delay="delay" @endGame="endGame" />
  <GameResult v-if="end && isPlaying === false" :score="score" />
</template>

<script>
import ClickBlock from "./components/ClickBlock.vue";
import GameResult from "./components/GameResult.vue";

export default {
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      end: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 3000;
    },

    endGame(score) {
      this.score = score;
      this.isPlaying = false;
      this.end = true;
    },
  },
  components: {
    ClickBlock,
    GameResult,
  },
};
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  text-align: center;
  color: rgb(53, 53, 53);
  margin-top: 60px;
}

button {
  font-weight: 700;
  width: 120px;
  height: 48px;
  background-color: aquamarine;
  border: 0;
  border-radius: 5px;
}

button:hover {
  background-color: rgb(116, 232, 193);
}

button:active{
  transform: scale(0.95);
}
</style>