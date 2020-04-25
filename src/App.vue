<template>
<v-app>
  <div id="app">
  <link href="https://fonts.googleapis.com/css?family=Material+Icons" rel="stylesheet">    <Fish />
  </div>
</v-app>
</template>

<script>
import Vuetify from 'vuetify';
import Fish from './components/Fish.vue';

export default {
  name: 'App',
  vuetify: new Vuetify(),
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
