<template lang="pug">
  #app
    <div class="swiper-container" ref="slider">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="slide in slides">
                <img :src="slide.img_url"/>
            </div>
        </div>
        <div class="swiper-pagination" ref="pagination"></div>
    </div>
</template>
<script>
import Swiper from 'swiper'
import 'swiper/dist/css/swiper.css'
export default {
  data () {
    return {
      slides: [
          { id: 1, img_url: '../src/assets/1.jpg'},
          { id: 1, img_url: '../src/assets/2.jpg'},
          { id: 1, img_url: '../src/assets/3.jpg'},
          { id: 1, img_url: '../src/assets/4.jpg'}
      ]
    }
  },
  mounted () {
    new Swiper(this.$refs.slider, {
      pagination: {
          el: this.$refs.pagination,
          type : 'progressbar',
          //type: 'bullets',
          //type: 'fraction',
          //type : 'custom',
      },
      effect : 'flip',
      paginationClickable: true,
      speed: 2000,
      loop: true,
      observer:true,
      observeParents:true,
      autoplayDisableOnInteraction : false,
      autoplay: {
          delay: 1000,
          stopOnLastSlide: false,
          disableOnInteraction: true,
      }
    })
  }
}
</script>

<style>
.swiper-container {
        width: 100%;
        margin: 0;
        padding: 0;
    }
    .swiper-wrapper {
        height: 500px;
    }
    .swiper-slide img {
        max-width: 100%;
    }
</style>
