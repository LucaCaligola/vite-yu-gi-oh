<script>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
    
  },

  methods: {
    getCard() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      
      .then((response) => {
        // handle success
        console.log(response.data.data);
        this.cards = response.data.data;
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

  data() {
    return {
      cards: [],
    }
  },

  created() {
    this.getCard();
    
  }


}


</script>

<template>
  
 
  <AppHeader/>
  <AppMain :cards="cards"/>


</template>

<style scoped>

</style>
