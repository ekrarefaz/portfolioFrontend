<template>
    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="8">
          <v-card class="text-center pa-5" color="#424242" dark>
            <v-icon size="56" class="mb-2">mdi-progress-wrench</v-icon>
            <h2 class="headline mb-3">Work in Progress</h2>
            <p class="subheading mb-4">I'm currently working on some exciting projects! Check back soon for updates.</p>
            <v-btn color="#33ff33" :href="githubUrl" large>
              <v-icon left>mdi-github</v-icon>
              Visit My GitHub
            </v-btn>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        githubUrl: 'https://github.com/ekrarefaz', // Replace with your GitHub profile URL
      };
    },
  };
  </script>
  
  <style scoped>
  </style>
  