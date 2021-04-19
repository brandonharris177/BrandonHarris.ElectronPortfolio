<template>
  <QRCodes/>
  <a href="https://github.com/brandonharris177/"> GitHub </a>
  <a href="https://www.linkedin.com/in/brandon-harris177/"> LinkedIn </a>
  <a href="mailto:brandonharris177@gmail.com"> brandonharris177@gmail.com </a>
  <a href="https://drive.google.com/file/d/1o_Qz3WAUTVgcdZk7os_WQ4p_IO_Gtc_L/view?usp=sharing"> Resume </a>
  <a class="twitter-timeline" href="https://twitter.com/BBCAfrica?ref_src=twsrc%5Etfw">Tweets by BBCAfrica</a>
  <a class="twitter-timeline" href="https://twitter.com/ethereum?ref_src=twsrc%5Etfw">Tweets by ethereum</a>
</template>

<script>
import QRCodes from './components/QRCodes.vue';

export default {
  name: 'App',
  components: {
    QRCodes,
  },
  mounted() {
    let externalScript = document.createElement('script')
    externalScript.setAttribute('src', 'https://platform.twitter.com/widgets.js')
    document.head.appendChild(externalScript)
  },
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
