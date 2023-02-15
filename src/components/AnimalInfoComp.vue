<template>
  <div class="col animal-card" v-bind:key="an" v-for="an in ans">
    <div class="row">
      <div class="col-md-4">
        <img src="" alt="">
      </div>
      <div class="col">
        {{ an.text }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    ans: {
      type: Array,
      required: true
    }
  }
}
</script>
<style scoped>
</style>
