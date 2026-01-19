<template>
  <div :class="$style.badge">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'ResumeBadge'
}
</script>

<style lang="scss" module>
@import '@/assets/scss/colors.scss';

.badge {
  display: inline-block;
  padding: 10px;
  background-color: transparent;
  border-radius: 8px;
  border: 2px solid $main;
  font-size: 14px;
  color: $main;
}
</style>
