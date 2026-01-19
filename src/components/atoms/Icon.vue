<template>
  <img :src="iconSrc" :alt="alt" :class="$style.icon" />
</template>

<script>
export default {
  name: 'ResumeIcon',
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      default: ''
    }
  },
  computed: {
    iconSrc() {
      // Используем динамический импорт для SVG
      return require(`@/assets/img/${this.src}.svg`)
    }
  }
}
</script>

<style lang="scss" module>
.icon {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}
</style>
