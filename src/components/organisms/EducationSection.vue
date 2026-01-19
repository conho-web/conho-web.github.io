<template>
  <section :class="$style.educationSection">
    <SectionHeader icon="education" title="Education" />
    <div :class="$style.educationContent">
      <div :class="$style.educationPeriod">{{ period }}</div>
      <p :class="$style.educationText">{{ text }}</p>
    </div>
  </section>
</template>

<script>
import SectionHeader from '@/components/molecules/SectionHeader.vue'

export default {
  name: 'EducationSection',
  components: {
    SectionHeader
  },
  props: {
    period: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" module>
@import '@/assets/scss/colors.scss';

.educationSection {
  background-color: $primary;
  border-radius: 20px;
  padding: 30px;
}

.educationContent {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.educationPeriod {
  font-size: 16px;
  font-weight: 500;
  color: $main;
}

.educationText {
  font-size: 16px;
  line-height: 1.6;
  color: $main;
  margin: 0;
}
</style>
