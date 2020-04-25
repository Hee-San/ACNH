<template>
  <p>{{ info }}</p>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      info: null,
    };
  },
  mounted() {
    axios
      .get('https://raw.githubusercontent.com/Hee-San/ACNH_data/master/fishes.json')
      .then((response) => { this.info = response; });
  },
};
</script>
<style>
</style>
