<script setup>
import { ref } from 'vue'

const props = defineProps({
  imageId: {
    type: String,
    default: 'card-img',
  },
  imgSrc: {
    type: String,
    default: '',
  },
  caption: {
    type: String,
    default: 'texto de ejemplo',
  },
})

ref(props.imgSrc)
</script>

<template>
  <div class="card text-center m-5 p-3 col-4 rounded">
    <img :id="imageId" :src="imgSrc" class="card-img-top" alt="..." @click="changeImg" />
    <div class="card-body">
      <p class="card-text">{{ caption }}</p>
    </div>
  </div>
</template>
<style scoped></style>
