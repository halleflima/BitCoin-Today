<template>

  <div id="moeda-valor">

    <h1> Preços do BitCoin </h1>
    <div v-for="currency in info" :key="currency" class="currency">
      {{ currency.description }}
      <span class="lighten">
        <span v-html="currency.symbol"></span> {{currency.rate_float | currencydecimal }}
      </span>
    </div>
  </div>

</template>

<script>
import axios from 'axios';
  export default {
    data() {
      return{
        info: null
      }
    },
    filters: {
      currencydecimal (value) {
        return value.toFixed(2);
      }
    },
    mounted(){
      axios
        .get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then(response => (this.info = response.data.bpi))
    },
    

  }
</script>

<style scoped>

  #moeda-valor{
  font-size: 180%;
  margin-top: 145px;
  width: 500px; 
  padding: 25px 40px 40px;
  background: #2F242C;
  border-radius: 5px;
  color: #B3BFB8;

  margin-left: 27%;
  margin-right: 35%;
  }

</style>