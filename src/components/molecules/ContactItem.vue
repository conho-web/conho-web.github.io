<template>
  <component
    :is="tag"
    :href="href"
    :class="$style.contactItem"
  >
    <ResumeIcon :src="icon" :alt="text" />
    <span>{{ text }}</span>
  </component>
</template>

<script>
import ResumeIcon from '@/components/atoms/Icon.vue'

export default {
  name: 'ContactItem',
  components: {
    ResumeIcon
  },
  props: {
    icon: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    href: {
      type: String,
      default: null
    }
  },
  computed: {
    tag() {
      return this.href ? 'a' : 'div'
    }
  }
}
</script>

<style lang="scss" module>
@import '@/assets/scss/colors.scss';

.contactItem {
  display: flex;
  align-items: center;
  gap: 12px;
  color: $main;
  text-decoration: none;
  font-size: 14px;
  transition: opacity 0.2s;

  &:hover {
    opacity: 0.7;
  }

  span {
    word-break: break-word;
  }
}
</style>
