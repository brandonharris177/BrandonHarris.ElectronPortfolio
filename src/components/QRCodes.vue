<template>
  <div class = "qrcode">
    <h1>
      Brandon Harris
    </h1>
    <qrcode-vue :value="value" :size="size" level="H" class = "qrcode"/>
  </div>
  <div class = "qrcode">
    <h1>
      Tezos Price
    </h1>
    <qrcode-vue :value= "'$' + tezos_price.toString() + 'USD'" :size="size" level="H" class = "qrcode"/>
  </div>
  <div class = "qrcode">
    <h1>
      Burst Price
    </h1>
    <qrcode-vue :value= "'$' + burst_price.toString() + 'USD'" :size="size" level="H" class = "qrcode"/>
  </div>
  <div class = "qrcode">
    <h1>
      Cardano Price
    </h1>
    <qrcode-vue :value= "'$' + cardano_price.toString() + 'USD'" :size="size" level="H" class = "qrcode"/>
  </div>
</template>
<script>
  import QrcodeVue from 'qrcode.vue';
  import axios from 'axios';

  export default {
    data() {
      return {
        value: 'Brandon Harris',
        size: 400,
        tezos_price: "",
        burst_price: "",
        cardano_price: "",
      }
    },
    methods: {
      coinGeckoAPIcall: function() {
         axios
        .get('https://api.coingecko.com/api/v3/coins/tezos')
        .then(response => (this.tezos_price = response.data.market_data.current_price.usd))
        .catch(error => console.log(error))
      axios
        .get('https://api.coingecko.com/api/v3/coins/cardano')
        .then(response => (this.cardano_price = response.data.market_data.current_price.usd))
        .catch(error => console.log(error))
      axios
        .get('https://api.coingecko.com/api/v3/coins/burst')
        .then(response => (this.burst_price = response.data.market_data.current_price.usd))
        .catch(error => console.log(error))
      },
      intervalFetchData: function() {
        setInterval(() => {
          this.coinGeckoAPIcall();
          //warning that application is currently refreshing, set to 5 second intervals right now, can be changed to refresh more or less frequently
          // console.log("CAUTION: currently making calls")
        }, 5000); //change number here measured in 1/1000 of a second to change the refresh rate
      }
    },
    mounted () {
        this.coinGeckoAPIcall();
        //turn off next line to disable auto-refresh
        this.intervalFetchData();
      },
    components: {
      QrcodeVue,
    },
  }
</script>

<style>
div.qrcode {
  width: 50%;
}
</style>