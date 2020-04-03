<template>
  <div>
    <section class="hero ">
      <div class="hero-body">
        <div class="container">
          <div class="columns">
            <div class="column is-8 is-offset-2">
              <figure class="image is-16by9">
                <img :src="primarySrc">
              </figure>
            </div>
          </div>
        </div>
      </div>  
    </section>  
    <div class="is-divider"></div>
    <section> 
      <vueper-slides
        class="no-shadow"
        :visible-slides="4"
        slide-multiple
        :gap="3"
        :arrows-outside="false"
        :slide-ratio="1 / 4"
        :dragging-distance="200"
        :breakpoints="{ 800: { visibleSlides: 3, slideMultiple: 1 } }">
        <vueper-slide v-for="(slide, i) in slides" 
          :key="i" 
          :title="slide.title" 
          :image="slide.src"
          @click.native="handleClick(slide)"/>
      </vueper-slides>
    </section>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default {
  components: { VueperSlides, VueperSlide },
  data: () => ({
  primarySrc: '',
  slides: [
    {
      title: 'Slide #1',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/32d160/FFFFFF'
    },
    {
      title: 'Slide #2',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/E6A2FF/FFFFFF'
    },
    {
      title: 'Slide #3',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/ffe500/FFFFFF'
    },
    {
      title: 'Slide #4',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/DDBBFF/FFFFFF'
    },
    {
      title: 'Slide #5',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/FF7145/FFFFFF'
    },
    {
      title: 'Slide #6',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/A2C423/FFFFFF'
    },
    {
      title: 'Slide #7',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/7C4326/FFFFFF'
    },
    {
      title: 'Slide #8',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/2E4500/FFFFFF'
    },
    {
      title: 'Slide #9',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/CCF4FE/FFFFFF'
    },
    {
      title: 'Slide #10',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/924F9E/FFFFFF'
    },
    {
      title: 'Slide #11',
      content: 'Slide content.',
      src: 'https://via.placeholder.com/150/D93D27/FFFFFF'
    }
  ],
}),
methods: {
  handleClick(slide) { 
    console.log(slide)
    this.primarySrc = slide.src
  }
}
  
}
</script>

<style>
  .vueperslides__arrow {color: white}
  .vueperslides__arrow svg {stroke-width: 2;}
</style>
