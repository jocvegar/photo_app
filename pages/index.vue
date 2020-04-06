<template>
  <div class="container has-text-centered">
    <div>
      <h1 class="title">
        eFe
      </h1>
      <h4 class="subtitle has-text-grey-lighter has-text-weight-semibold">
        "Pedacitos de tiempo que vivimos con cada persona [...] No importa la cantidad de tiempo que pasamos con cada amigo, si no la calidad del tiempo que vivimos con él [...] Cinco minutos pueden tener una importancia mayor que un día entero..." 
        <br>
        <br>
        -El Principito
      </h4>
      <slider></slider>
    </div>
  </div>
</template>

<script>

import Slider from '~/components/Slider.vue'
export default {
  components: {
    Slider,
  },
}
</script>

<style scoped>
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #dbdbdb;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  word-spacing: 5px;
  padding-bottom: 15px;
  padding-top: 15px;
}
.big-me {
  height: 100vh;
}
</style>
