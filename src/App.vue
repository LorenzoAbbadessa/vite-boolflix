<script>

import { store } from './components/store.js'
import axios from 'axios';

export default {
  data() {
    return {
      store,
    }
  },
}
const options = {
  method: 'GET',
  url: 'https://api.themoviedb.org/3/authentication',
  headers: {
    accept: 'application/json',
    Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI2N2I0ZDM1ZmRiZThjNzQ0ZjlhZjhhYWE0Y2M0MDMyZSIsInN1YiI6IjY1NmRkY2JlM2RjMzEzMDBlMWVlOTdiNCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.k1By06hgxySVaizPmjXAkNlNBLe6Fctpai_fwoc-avA'
  }
};

axios
  .request(options)
  .then(function (response) {
    console.log(response.data);
  })
  .catch(function (error) {
    console.error(error);
  });

</script>



<template>
  <input type="text" placeholder="search" v-model="store.searchText" @keyup.enter="$emit('GET')">
  <button>GO!</button>
</template>



<style scoped></style>