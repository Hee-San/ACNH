<template>
<div id="fish">
  <v-container>
      <v-row dense>
        <v-col cols="6" sm="3" lg="2" v-for="(fish, key) in fishes" :key="key">
          <v-card color="#EDE7C8">
            <v-list-item three-line>
              <v-list-item-content>
                <div class="overline font-weight-bold">{{fish.Name}}</div>
                <v-list-item-subtitle class="headline">
                  <v-icon>account_balance</v-icon>
                </v-list-item-subtitle>
              </v-list-item-content>
              <v-list-item-avatar tile size="80">
                <v-img :src="fish.imgsrc" class="align-end"></v-img>
              </v-list-item-avatar>
            </v-list-item>
            <v-card-actions>
      <v-btn text small color="primary" @click="overlay = !overlay; idx=key">
        Learn More
      </v-btn>
    </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
  </v-container>
  <v-overlay :value="overlay">
      <v-btn icon @click="overlay = false">
        <v-icon>close</v-icon>
      </v-btn>
      <v-img :src="fishes[idx].imgsrc" class="align-end"></v-img>
      <p>Name:{{fishes[idx].Name}}</p>
      <p>Size:{{fishes[idx].Size}}</p>
      <p>Cost:{{fishes[idx].Cost}}</p>
      <p>Place:{{fishes[idx].Place}}</p>
      <p>Season:{{fishes[idx].Season}}</p>
      <p>Time:{{fishes[idx].Time}}</p>
    </v-overlay>
  <!-- <table>
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
  </table> -->
  <!-- <p>{{ fishes }}</p> -->
</div>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      fishes: null,
      overlay: false,
      idx: 0,
    };
  },
  mounted() {
    axios
      .get('https://raw.githubusercontent.com/Hee-San/ACNH_data/master/fishes.json')
      .then((response) => {
        this.fishes = response.data;
        for (let i = 0; i < this.fishes.length; i += 1) {
          // https://raw.githubusercontent.com/Hee-San/ACNH_data/master/pictures/%E3%82%A2%E3%82%B8.jpeg
          this.fishes[i].imgsrc = `https://raw.githubusercontent.com/Hee-San/ACNH_data/master/pictures/${
            this.fishes[i].Name}.jpeg`;
        }
      });
  },
};
</script>
<style>
</style>
