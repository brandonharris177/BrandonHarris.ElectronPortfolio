<template>
  <h1>
    Brandon Harris
  </h1>
  <qrcode-vue :value="value" :size="size" level="H" />
  <h1>
    Tezos Price
  </h1>
  <qrcode-vue :value= tezos_price.toString() :size="size" level="H" />
  <h1>
    Burst Price
  </h1>
  <qrcode-vue :value= burst_price.toString() :size="size" level="H" />
  <h1>
    Cardano Price
  </h1>
  <qrcode-vue :value= cardano_price.toString() :size="size" level="H" />
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
    mounted () {
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
    components: {
      QrcodeVue,
    },
  }
</script>