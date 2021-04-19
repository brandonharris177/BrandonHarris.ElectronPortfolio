<template>
  <div class = "body">
    <QRCodes/>
    <div class = "tweets">
      <div class = "tweet">
        <a class="twitter-timeline" href="https://twitter.com/BBCAfrica?ref_src=twsrc%5Etfw">Tweets by BBCAfrica</a>
      </div>
      <div class = "tweet">
        <a class="twitter-timeline" href="https://twitter.com/ethereum?ref_src=twsrc%5Etfw">Tweets by ethereum</a>
      </div>
    </div>
    <div class = "links">
      <a class="link" href="https://github.com/brandonharris177/"> GitHub </a>
      <a class= "link" href="https://www.linkedin.com/in/brandon-harris177/"> LinkedIn </a>
      <a class= "link" href="mailto:brandonharris177@gmail.com"> brandonharris177@gmail.com </a>
      <a class= "link" href="https://drive.google.com/file/d/1o_Qz3WAUTVgcdZk7os_WQ4p_IO_Gtc_L/view?usp=sharing"> Resume </a>
    </div>
  </div>
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
div.body {
  display: flex;
  flex-flow: row wrap;
  width: 100%;
  justify-content: center;
}
div.tweets{
  display: flex;
  align-content: center;
  width: 90%;
  margin: 30px;
  justify-content: space-around;
}
div.tweet{
  width: 40%;
}
div.links{
  display: flex;
  flex-flow: column;
}

</style>
