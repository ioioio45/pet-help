<template>
    <div class="video-list self-center" style="">
          <video-player style="width: 100%" class="video-player-box video-js" ref="videoPlayer" :options="playerOptions" />
    </div>
  </template>
<script>
import VideoPlayer from './VideoPlayer.vue'

// Import Swiper styles
export default {
  components: {
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
      playerOptions: {
        // videojs options
        autoplay: true,
        loop: true,
        language: 'en',
        muted: false,
        playbackRates: [0.7, 1.0, 1.5, 2.0],
        sources: [{
          type: 'video/mp4',
          src: require(
            '../assets/videos/video.mp4'
          )
        }]
      }
    }
  }
}
</script>

  <style scoped>
.video-list{
  z-index:1;
}

  </style>
