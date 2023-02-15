<template>
  <div class="video-list">
     <swiper class="swiper" :options="swiperOption">
      <swiper-slide>
        <video-player style="" class="video-player-box video-js" ref="videoPlayer" :options="playerOptions"/>
      </swiper-slide>
    </swiper>
  </div>
  </template>
<script>
import { Swiper, SwiperSlide } from 'swiper/vue'
import VideoPlayer from './VideoPlayer.vue'

// Import Swiper styles
import 'swiper/css'
export default {
  components: {
    Swiper,
    SwiperSlide,
    VideoPlayer
  },
  setup () {
    const onSwiper = (swiper) => {
      console.log(swiper)
    }
    const onSlideChange = () => {
      console.log('slide change')
    }
    return {
      onSwiper,
      onSlideChange
    }
  },
  data () {
    return {
      swiperOption: {
        direction: 'vertical',
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      },
      playerOptions: {
        // videojs options
        autoplay: true,
        controls: false,
        loop: true,
        language: 'en',
        muted: false,
        playbackRates: [0.7, 1.0, 1.5, 2.0],
        sources: [{
          type: 'video/mp4',
          src: 'https://joy1.videvo.net/videvo_files/video/free/2014-12/large_watermarked/Raindrops_Videvo_preview.mp4'
        }]
      }
    }
  }
}
</script>

  <style scoped>
.video-list{
  z-index:2
}

swiper-container
{
  height: 100%;

}

.swiper-wrapper{
  height: 100%;
}

  .swiper-slide{
  height:  100%;
  position: relative;
  color: #ffffff;
}

  </style>
