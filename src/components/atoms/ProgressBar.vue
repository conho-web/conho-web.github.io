<template>
  <div :class="[$style.progressBar, $style[progressClass]]">
    <div :class="$style.progressFill" :style="{ width: `${percentage}%` }"></div>
  </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: {
    percentage: {
      type: Number,
      required: true,
      validator: (value) => value >= 0 && value <= 100
    }
  },
  computed: {
    progressClass() {
      if (this.percentage >= 60) return 'progressHigh'
      if (this.percentage >= 30) return 'progressMedium'
      return 'progressLow'
    }
  }
}
</script>

<style lang="scss" module>
@import '@/assets/scss/colors.scss';

.progressBar {
  height: 8px;
  background-color: $primary;
  border-radius: 4px;
  overflow: hidden;
}

.progressFill {
  height: 100%;
  border-radius: 4px;
  transition: width 0.3s ease;
}

.progressLow {
  .progressFill {
    background-color: #FF4444;
  }
}

.progressMedium {
  .progressFill {
    background-color: #FFA500;
  }
}

.progressHigh {
  .progressFill {
    background-color: #00C851;
  }
}
</style>
