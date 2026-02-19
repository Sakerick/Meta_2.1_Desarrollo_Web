<script setup>
import CardImg from './CardImgComp.vue'
import TableComp from './TableComp.vue'

function showAlert() {
  alert('¡Botón clickeado!')
}

function getImageUrl(isBlurry) {
  const params = isBlurry === 'true' ? 'blur&t=' : 't='
  return `https://picsum.photos/600/400?${params}${Math.random()}`
}
</script>
<template>
  <div class="container p-2">
    <div class="row justify-content-around align-items-center">
      <CardImg
        imageId="card1"
        :imgSrc="getImageUrl('true')"
        caption="Aqui se muestra una imagen aleatoria obtenida de
          lorem picsum, al hacer click en la imagen se cambia por otra imagen
          aleatoria"
      />

      <CardImg
        imageId="card2"
        :imgSrc="getImageUrl('false')"
        caption="Aqui se muestra una imagen aleatoria con efecto blur obtenida de
          lorem picsum, al hacer click en la imagen se cambia por otra imagen
          aleatoria"
      />

      <TableComp />
      <button type="button" class="btn btn-primary btn-lg w-auto m-3" @click="showAlert()">
        Un botonsillo
      </button>
    </div>
  </div>
</template>
