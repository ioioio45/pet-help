<template>
  <div>
    <swiper class="swiper" :options="swiperOption" :slides-per-view="1" :space-between="0" :direction="'vertical'">
      <swiper-slide>
          <sideicons style="position: absolute"/>
          <VideoList/>
      </swiper-slide>
      <swiper-slide>
          <sideicons style="position: absolute"/>
          <VideoList/>
      </swiper-slide>
      <swiper-slide>
          <sideicons style="position: absolute"/>
          <VideoList/>
      </swiper-slide>
    </swiper>
  </div>

</template>

<script>
import sideicons from 'components/SideIcons.vue'
import VideoList from 'components/VideoList.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'

import 'swiper/css'

export default {
  components: {
    sideicons,
    VideoList,
    Swiper,
    SwiperSlide
  },
  props: {
    posts: {
      type: Array,
      required: true
    }
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
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
p {
  text-align: center;
}
swiper-slide{
  height:  100%;
  position: relative;
  color: #ffffff;
}
</style>
