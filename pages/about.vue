<template>
    <div class="container">
        <section class="section has-text-centered">
        <div class="container">
            <h1 class="title has-text-success">Section</h1>
            <h2 class="subtitle has-text-white-ter">
                A simple container to divide your page into sections, like the one you're currently reading
            </h2>
        </div>
        <slider></slider>
    </section>
    </div>
</template>

<style lang="scss">
</style>

<script>
import Slider from '~/components/Slider.vue'
import Photo from '~/components/Photo.vue'

export default {
  components: {
    Slider,
    Photo
  }
}

</script>
