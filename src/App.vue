<template>
  <QRCodes msg="Name"/>
</template>

<script>
import QRCodes from './components/QRCodes.vue';

export default {
  name: 'App',
  components: {
    QRCodes,
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
