<template>
  <div class="container has-text-centered">
    <div>
      <h1 class="title">
        eFe
      </h1>
      <h4 class="subtitle has-text-grey-lighter">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla, dolores? Neque dolorem repellendus, voluptas eveniet sequi expedita voluptate iste sit nemo, reiciendis doloribus, minus magni magnam omnis unde necessitatibus asperiores.
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
  }
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
}
</style>
