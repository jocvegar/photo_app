<template>
  <div>
    <section class="hero">
      <div class="hero-body">
        <div class="container">
          <div class="columns">
            <div class="column is-8 is-offset-2">
              <figure class="image">
                 <img :src="primarySrc">
              </figure>
            </div>
          </div>
        </div>
      </div>  
    </section>  
    <div class="column is-6 is-offset-3">
      <button 
          class="button is-dark is-medium is-fullwidth"
          @click="$refs.myVueperSlides[`${autoPlaying ? 'pause' : 'resume'}Autoplay`]();autoPlaying = !autoPlaying">
          {{ autoPlaying ? 'Pause' : 'Resume' }}
        </button>
    </div>  
      <br>
    <div class="is-divider"></div>
    <section> 
      <vueper-slides
        ref="myVueperSlides"
        class="no-shadow slides-container"
        :visible-slides="4"
        :slide-multiple="false"
        fractions
        progress
        lazy 
        lazy-load-on-drag
        :gap="3"
        :arrows-outside="false"
        :slide-ratio="1 / 8"
        :bullets="false"
        :dragging-distance="200"
        autoplay
        @autoplay-pause="internalAutoPlaying = false"
        @autoplay-resume="internalAutoPlaying = true"
        :breakpoints="{ 800: { visibleSlides: 3 } }"
        @slide="updateImageFromSlide($event.currentSlide)">
        <vueper-slide v-for="(slide, i) in slides"
          :key="i" 
          :image="require(`~/assets/images/pic_${slide.src}.jpg`)"
          @click.native.prevent="updateImageFromClick(slide)"/>
      </vueper-slides>
      <br>
    </section>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
let dataSet = []

export default {
  components: { VueperSlides, VueperSlide },
  data: () => ({
    autoPlaying: true,
    internalAutoPlaying: true,
    primarySrc: '',
    slideConstructor: [],
    slides: dataSet,
  }),
  methods: {
    updateImageFromClick(slide) { 
      this.primarySrc = require(`~/assets/images/pic_${slide.src}.jpg`)   
    },
    updateImageFromSlide(slide) {
      // console.log(slide)
      this.primarySrc = require(`~/assets/images/pic_${slide.index + 1}.jpg`)   
    }
  },
  created() {
    this.primarySrc = require('~/assets/images/pic_1.jpg') 
  },
  beforeCreate() {
    let arr = new Array(126).join().split(',').map(function(item, index){ return ++index;})
    arr.forEach(num => {
      dataSet.push({ src: num.toString() })
    })
  }
}
</script>

<style>
  .vueperslides__arrow {color: white}
  .vueperslides__arrow svg {stroke-width: 2;}
  .vueperslides__progress {
    background: rgba(0, 0, 0, 0.25);
    color: #DBDBDB;
  }
  .slides-container {
    padding-bottom: 5em;
  }
</style>
