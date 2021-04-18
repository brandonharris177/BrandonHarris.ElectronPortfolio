<template>
  <qrcode-vue :value="value" :size="size" level="H" />
</template>
<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: 'Brandon Harris',
        size: 400,
      }
    },
    components: {
      QrcodeVue,
    },
  }
</script>