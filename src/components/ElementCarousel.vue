<template>
  <div>
    <Carousel class="slider">
      <Slide v-for="img in elem.images" :key=" img">
        <div class="slider-card">
          <img :alt="elem.name" :src="img"/>
        </div>
      </Slide>
      <template #addons>
        <Navigation/>
      </template>
    </Carousel>
  </div>
</template>

<script>
import {Carousel, Navigation, Slide} from 'vue3-carousel';
import 'vue3-carousel/dist/carousel.css';

export default {
  name: 'element-carousel',
  components: {
    Carousel, Slide, Navigation
  },
  props: {
    elem: {}
  }
}
</script>

<style lang="scss">

.slider, .slider-card{
  width: 30rem;
  height: 25rem;
}
</style>
