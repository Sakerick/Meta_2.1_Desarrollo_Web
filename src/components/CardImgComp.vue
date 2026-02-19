<script setup>
import { ref } from 'vue'

const props = defineProps({
  imageId: {
    type: String,
    default: 'card-img',
  },
  imgSrc: {
    type: String,
    default: 'https://picsum.photos/600/400?random=' + Math.random(),
  },
  caption: {
    type: String,
    default: 'texto de ejemplo',
  },
})
const imgSrc = ref(props.imgSrc)

function getImageUrl() {
  imgSrc.value = `https://picsum.photos/600/400?random=${Math.random()}`
}

ref(props.imgSrc)
</script>

<template>
  <div class="card text-center m-5 p-3 col-4 rounded">
    <img :id="imageId" :src="imgSrc" class="card-img-top" alt="..." @click="getImageUrl()" />
    <div class="card-body">
      <p class="card-text">{{ caption }}</p>
    </div>
  </div>
</template>
<style scoped></style>
