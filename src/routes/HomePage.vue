<template>
  <div :class="$style.resume">
    <div :class="$style.container">
      <div :class="$style.topSection">
        <ProfileSidebar :contacts="resumeData.contacts" />

        <div :class="$style.rightColumn">
          <div :class="$style.nameBlock">
            <h1 :class="$style.name">{{ resumeData.personal.name }}</h1>
            <p :class="$style.title">{{ resumeData.personal.title }}</p>
          </div>

          <div :class="$style.aboutBlock">
            <AboutSection :paragraphs="resumeData.about" />
          </div>
        </div>
      </div>

      <WorkExperienceSection :work-experiences="resumeData.workExperience" />
      <SkillsSection :skills-categories="resumeData.skills" />
      <EducationSection
        :period="resumeData.education.period"
        :text="resumeData.education.text"
      />
    </div>
  </div>
</template>

<script>
import { resumeData } from '@/data/resume.js'
import ProfileSidebar from '@/components/organisms/ProfileSidebar.vue'
import AboutSection from '@/components/organisms/AboutSection.vue'
import WorkExperienceSection from '@/components/organisms/WorkExperienceSection.vue'
import SkillsSection from '@/components/organisms/SkillsSection.vue'
import EducationSection from '@/components/organisms/EducationSection.vue'

export default {
  name: 'HomePage',
  components: {
    ProfileSidebar,
    AboutSection,
    WorkExperienceSection,
    SkillsSection,
    EducationSection
  },
  data() {
    return {
      resumeData
    }
  }
}
</script>

<style lang="scss" module>
@import '@/assets/scss/colors.scss';
@import '@/assets/scss/fonts.scss';

.resume {
  min-height: 100vh;
  background-color: $background;
  padding: 20px;
}

.container {
  max-width: 910px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.topSection {
  display: grid;
  grid-template-columns: auto auto;
  gap: 20px;
}

.rightColumn {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.nameBlock {
  background-color: $primary;
  border-radius: 16px;
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
}

.name {
  font-family: 'Futura';
  font-weight: 700;
  font-size: 24px;
  color: $main;
}

.title {
  font-size: 20px;
  color: $main;
  margin: 0;
}

.aboutBlock {
  background-color: $primary;
  border-radius: 16px;
  padding: 20px;
  height: -webkit-fill-available;
}

@media (max-width: 968px) {
  .topSection {
    grid-template-columns: 1fr;
  }

  .nameBlock {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
