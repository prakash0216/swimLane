<template>
  <div class="swim-lane" ref="swimLane" tabindex="0" @keydown="handleKeydown">
    <swimLaneTitle />
    <div class="row-container">
      <row3 v-if="currentRow === 3" />
      <row4 v-if="currentRow === 4" />
    </div>
    <arrowButton
      v-if="currentRow === 4"
      direction="left"
      class="left-arrow"
      @navigate="showPreviousRow"
    >
      <
    </arrowButton>
    <arrowButton
      v-if="currentRow === 3"
      direction="right"
      class="right-arrow"
      @navigate="showNextRow"
    >
      >
    </arrowButton>
  </div>
</template>

<script>
import swimLaneTitle from './swimLaneTitle.vue'
import row3 from './row3.vue'
import row4 from './row4.vue'
import arrowButton from './arrowButton.vue'
import '../assets/swimLane.css'

export default {
  name: 'swimLane',
  components: {
    swimLaneTitle,
    row3,
    row4,
    arrowButton
  },
  data() {
    return {
      currentRow: 3
    }
  },
  methods: {
    showPreviousRow() {
      if (this.currentRow === 4) {
        this.currentRow = 3
      }
    },
    showNextRow() {
      if (this.currentRow === 3) {
        this.currentRow = 4
      }
    },
    handleKeydown(event) {
      if (event.key === 'ArrowRight') {
        this.showNextRow()
      } else if (event.key === 'ArrowLeft') {
        this.showPreviousRow()
      }
    }
  },
  mounted() {
    this.$refs.swimLane.focus()
  }
}
</script>
