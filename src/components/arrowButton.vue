<template>
  <button class="arrow-button" :class="direction" @click="navigate">
    <slot></slot>
  </button>
</template>

<script>
import '../assets/arrowButton.css'

export default {
  name: 'arrowButton',
  props: {
    direction: {
      type: String,
      required: true
    }
  },
  methods: {
    navigate() {
      this.$emit('navigate')
    }
  }
}
</script>
