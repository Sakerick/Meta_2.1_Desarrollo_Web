<script setup>
import { ref } from 'vue'

const props = defineProps({
  imageId: {
    type: String,
    default: 'card-img',
  },
  isBlurry: {
    type: String,
    default: 'true',
  },
  caption: {
    type: String,
    default: 'texto de ejemplo',
  },
})

const imgSrc = ref('')

function getImageUrl() {
  const params = props.isBlurry === 'true' ? 'blur&t=' : 't='
  return `https://picsum.photos/600/400?${params}${Math.random()}`
}

function changeImg() {
  imgSrc.value = getImageUrl()
  console.log('Imagen cambiada a: ' + imgSrc.value)
}

// Cargar imagen en el montaje
imgSrc.value = getImageUrl()
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
