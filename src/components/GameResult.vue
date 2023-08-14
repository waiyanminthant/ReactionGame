<template>
  <p>Your reaction time is {{ score }} miliseconds.</p>
  <h3 v-if="score < 1000">Fastest hand in the west!</h3>
  <h3 v-else-if="1000 < score < 2000">Uhh... Not bad kid...</h3>
  <h3 v-else>Slow Poke!</h3>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style>
</style>