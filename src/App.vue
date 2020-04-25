<template>
  <div id="app">
    <Fish />
  </div>
</template>

<script>
import Fish from './components/Fish.vue';

export default {
  name: 'App',
  components: {
    Fish,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
