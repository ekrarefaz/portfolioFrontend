<template>
    <v-container>
      <v-tabs v-model="tab">
        <v-tab v-for="item in tabs" :key="item">
          {{ item }}
        </v-tab>
      </v-tabs>
  
      <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in tabs" :key="item">
          <!-- You can add your custom content for each tab here -->
          <div v-if="item === 'About'">
            <!-- About content -->
          </div>
          <div v-if="item === 'Experience'">
            <ExperienceSectionComponent/>
          </div>
          <div v-if="item === 'Certification'">
            <!-- Certification content -->
          </div>
          <div v-if="item === 'Projects'">
            <!-- Projects content -->
          </div>
          <div v-if="item === 'Education'">
            <!-- Education content -->
          </div>
        </v-tab-item>
      </v-tabs-items>
    </v-container>
  </template>
  
  <script>

  import ExperienceSectionComponent from '@/components/AboutComponents/ExperienceSectionComponent.vue'

  export default {
    data() {
      return {
        tab: null,
        tabs: ['About', 'Experience', 'Certification', 'Projects', 'Education']
      };
    },
    components: {
      ExperienceSectionComponent
    }
  };
  </script>
  