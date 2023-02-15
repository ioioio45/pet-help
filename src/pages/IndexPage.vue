<template>
  <q-page class="flex flex-center">
    <div class="column">
      <VideoBox :posts ="posts"/>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import VideoBox from 'src/components/VideoBox.vue'

export default defineComponent({
  name: 'IndexPage',

  components: {
    VideoBox
  },
  data () {
    return {
      posts: [
        { id: 1, title: 'Заголовок', body: 'Описание поста' },
        { id: 2, title: 'Заголовок', body: 'Описание поста' },
        { id: 3, title: 'Заголовок', body: 'Описание поста' }
      ],
      title: '',
      body: ''
    }
  },
  methods: {
    createPost () {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      }
      this.posts.push(newPost)
      this.title = ''
      this.body = ''
    }
  }
})
</script>
