<template>
  <div>
    <div class="column">
      <AnimalInfoComp/>
    </div>
  </div>
</template>
<script>
import AnimalInfoComp from 'src/components/VideoBox.vue'
import { defineComponent } from 'vue'

export default defineComponent({
  components: {
    AnimalInfoComp
  },
  data () {
    return {
      an: [
        { id: 1, text: 'Заголовок', img: 'Описание поста' },
        { id: 2, text: 'Заголовок', img: 'Описание поста' },
        { id: 3, text: 'Заголовок', img: 'Описание поста' }
      ],
      text: '',
      img: ''
    }
  }
}

)

</script>
