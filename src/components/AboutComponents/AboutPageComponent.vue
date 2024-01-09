<template>
    <v-container>
      <v-tabs v-model="tab">
        <v-tab v-for="item in tabs" :key="item">
          {{ item }}
        </v-tab>
      </v-tabs>
  
      <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in tabs" :key="item">
          <component :is="currentTabComponent"></component>
        </v-tab-item>
      </v-tabs-items>
    </v-container>
  </template>
  

<script>
import AboutComponent from '@/components/AboutComponents/MainSectionComponent.vue';
import ExperienceSectionComponent from '@/components/AboutComponents/ExperienceSectionComponent.vue';
import ProjectsComponent from '@/components/AboutComponents/ProjectsComponent.vue';

export default {
  data() {
    return {
      tab: null,
      tabs: ['About', 'Experience', 'Projects',]
    };
  },
  components: {
    AboutComponent,
    ExperienceSectionComponent,
    ProjectsComponent,
  },
  computed: {
    currentTabComponent() {
      switch (this.tabs[this.tab]) {
        case 'About': return AboutComponent;
        case 'Experience': return ExperienceSectionComponent;
        case 'Projects': return ProjectsComponent;
        default: return null;
      }
    }
  }
};
</script>


  