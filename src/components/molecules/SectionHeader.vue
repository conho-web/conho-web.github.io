<template>
  <div :class="$style.sectionHeader">
    <ResumeIcon :src="icon" :alt="title" />
    <h2>{{ title }}</h2>
  </div>
</template>

<script>
import ResumeIcon from '@/components/atoms/Icon.vue'

export default {
  name: 'SectionHeader',
  components: {
    ResumeIcon
  },
  props: {
    icon: {
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

<style lang="scss" module>
@import '@/assets/scss/colors.scss';
@import '@/assets/scss/fonts.scss';

.sectionHeader {
  display: flex;
  align-items: center;
  gap: 6px;
  margin-bottom: 18px;

  h2 {
    font-family: 'Futura', sans-serif;
    font-weight: 500;
    font-size: 20px;
    color: $main;
    margin: 0;
  }
}
</style>
