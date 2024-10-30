<template>
  <div id="app">
    <BasketballPlayer />
  </div>
</template>

<script>
import BasketballPlayer from './components/BasketballPlayer.vue';

export default {
  components: {
    BasketballPlayer
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>