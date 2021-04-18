<template>
  <h1>
    Brandon Harris
  </h1>
  <qrcode-vue :value="value" :size="size" level="H" />
  <h1>
    Tezos
  </h1>
  <qrcode-vue :value="tezos_price" :size="size" level="H" />
  <h1>
    Burst
  </h1>
  <qrcode-vue :value="burst_price" :size="size" level="H" />
  <h1>
    Cardano 
  </h1>
  <qrcode-vue :value="cardano_price" :size="size" level="H" />
</template>
<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: 'Brandon Harris',
        size: 400,
        tezos_price: 'Tezos Price',
        burst_price: 'Burst Price',
        cardano_price: 'Cardano Price',
      }
    },
    components: {
      QrcodeVue,
    },
  }
</script>