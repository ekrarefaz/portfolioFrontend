<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6" class="text-md-left text-center">
        <h1>Hello</h1>
        <h2>I'm Ekrar Efaz</h2>
        <p>Welcome to my digital domain, where passion for Cyber-Security and mastery in Computer Science converge.</p>
        <v-btn color="grey" dark>Download CV</v-btn>
      </v-col>
      <v-col cols="12" md="6" class="text-md-right text-center">
        <!-- Use the imported image here -->
        <img src="@/assets/profile-pic-nobg.png" class="profile-img"><img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// Make sure the import matches the file name and extension
import profilePic from '@/assets/profile-pic-nobg.png'

export default {
  data() {
    return {
      profilePic,
    }
  },
  name: 'HomePage'
}
</script>

<style scoped>
.profile-img {
  max-width: 300px; /* Adjust as needed */
  border-radius: 2%; /* Makes the image round */
  border: 1px solid #000;
  /* Add object-fit to ensure the image covers the area without distortion */
  object-fit: cover; 
}
</style>
