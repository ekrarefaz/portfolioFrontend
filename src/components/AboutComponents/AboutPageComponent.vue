<template>
    <v-container>
        <v-row justify="center">
            <v-col cols="12">
              <v-btn icon class="home-button" @click="goHome">
                <v-icon>mdi-home</v-icon>
              </v-btn>
            </v-col>
          </v-row>
  
      <v-tabs v-model="tab">
        <!-- Generate tabs -->
        <v-tab v-for="(item, index) in tabs" :key="`tab-${index}`">
          {{ item }}
        </v-tab>
      </v-tabs>
  
      <v-tabs-items v-model="tab">
        <!-- Single v-tab-item for each tab -->
        <v-tab-item v-for="(item, index) in tabs" :key="`tab-item-${index}`">
          <!-- Conditionally render the content based on the active tab index -->
          <div v-if="tab === index">
            <component :is="currentTabComponent"></component>
          </div>
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
        tabs: ['About', 'Experience', 'Projects']
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
    },
    methods: {
      goHome() {
        this.$router.push('/');
      }
    }
  };
  </script>
  
  <style scoped>
  .home-button {
    background-color: #212121; /* Green background */
    color: #ffff33; /* White icon */
    border-radius: 50%; /* Circular shape */
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2); /* Box shadow for depth */
    transition: background-color 0.3s, box-shadow 0.3s; /* Smooth transition for hover effects */
  }
  
  .home-button:hover {
    background-color: #45a049; /* Darker green on hover */
    color: white;
    box-shadow: 0 6px 12px 0 rgba(0,0,0,0.3); /* Larger shadow on hover */
  }
  </style>