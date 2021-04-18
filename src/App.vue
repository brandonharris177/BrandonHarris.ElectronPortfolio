<template>
  <QRCodeName msg="Name"/>
  <QRCodeTezos msg="Tezos Price"/>
  <QRCodeBurst msg="Burst Price"/>
  <QRCodeCardano msg="Cardano Price"/>
</template>

<script>
import QRCodeName from './components/QRCodeName.vue';
import QRCodeTezos from './components/QRCodeTezos.vue';
import QRCodeBurst from './components/QRCodeBurst.vue';
import QRCodeCardano from './components/QRCodeCardano.vue';

export default {
  name: 'App',
  components: {
    QRCodeName,
    QRCodeTezos,
    QRCodeBurst,
    QRCodeCardano
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
