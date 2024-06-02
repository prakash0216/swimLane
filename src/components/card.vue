<template>
  <div class="card">
    <img :src="imgSrc" class="card-img-top" :alt="title" />
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
    </div>
  </div>
</template>

<script>
import '../assets/card.css'

export default {
  name: 'BootstrapCard',
  props: {
    imgSrc: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  }
}
</script>
