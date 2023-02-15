<template>
  <div>
    <div
    class="Video-box column bg-primary"
    v-bind:key="post"
    v-for="post in posts"
  >
  <VideoList/>
  <sideicons/>
  <div class="justify-end column" style="height: 23vh">
    <VideoList/>
    <div class="text">
      <strong>
        <p class="title">{{ post.title }}</p>
      </strong>
      <p class="body">{{ post.body }}</p>
    </div>
    <bottommenu/>
  </div>

  </div>

  </div>

</template>

<script>
import bottommenu from 'components/BottomMenu.vue'
import sideicons from 'components/SideIcons.vue'
import VideoList from 'components/VideoList.vue'
export default {
  components: {
    bottommenu, sideicons, VideoList
  },
  props: {
    posts: {
      type: Array,
      required: true
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
.Video-box {
  height: 96vh;
  width: 100vw;
  border: 1px solid black
}
p {
  text-align: center;
}
sideicons {
  height: 70vh
}
</style>
