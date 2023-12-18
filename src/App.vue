<script setup>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain
  },

  methods: {
    getCard() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      
      .then(function (response) {
        // handle success
        console.log(response);
      })
      .catch(function (error) {
        // handle error
        console.error(error);
      })
      .finally(function () {
        // always executed
      });
    }
  },

  created() {
    
  }


}


</script>

<template>
  
 
  <AppHeader/>
  <AppMain/>


</template>

<style scoped>

</style>
