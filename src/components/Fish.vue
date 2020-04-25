<template>
<div id="fish">
  <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Picture</th>
        <th>Size</th>
        <th>Cost</th>
        <th>Place</th>
        <th>Season</th>
        <th>Time</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(fish, key) in fishes" :key="key">
        <td>{{fish.Name}}</td>
        <td>{{fish.Picture}}</td>
        <td>{{fish.Size}}</td>
        <td>{{fish.Cost}}</td>
        <td>{{fish.Place}}</td>
        <td>{{fish.Season}}</td>
        <td>{{fish.Time}}</td>
      </tr>
    </tbody>
  </table>
  <!-- <p>{{ fishes }}</p> -->
</div>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      fishes: null,
    };
  },
  mounted() {
    axios
      .get('https://raw.githubusercontent.com/Hee-San/ACNH_data/master/fishes.json')
      .then((response) => { this.fishes = response.data; });
  },
};
</script>
<style>
</style>
