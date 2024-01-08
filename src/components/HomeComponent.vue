<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6" class="text-md-left text-center align-self-center">
        <!-- Your text content -->
        <h1>{{ currentGreeting }}</h1>
        <h2>I'm Ekrar Efaz</h2>
        <p>Welcome to my digital domain, where passion for Cyber-Security and mastery in Computer Science converge.</p>
        <v-btn color="grey" dark>Download CV</v-btn>
      </v-col>
      <v-col cols="12" md="6" class="text-md-right text-center align-self-center">
        <!-- Your image -->
        <img :src="profilePic" class="profile-img">
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
      greetings: [
        'Hello',    // English
        'Hola',     // Spanish
        'Bonjour',  // French
        'Ciao',     // Italian
        'Hallo',    // German
        'Olá',      // Portuguese
        'Merhaba',  // Turkish
        'Hej',      // Danish
        'Hei',      // Norwegian
        'Sveiki',   // Latvian
        'Salaam',   // Arabic
    ],
      currentGreeting: 'Hello',
      greetingIndex: 0,
      interval: null
    }
  },
  methods: {
    changeGreeting() {
      this.greetingIndex = (this.greetingIndex + 1) % this.greetings.length;
      this.currentGreeting = this.greetings[this.greetingIndex];
    }
  },
  mounted() {
    this.interval = setInterval(this.changeGreeting, 4000); // Change every 2000 milliseconds (2 seconds)
  },
  beforeUnmount() {
    clearInterval(this.interval);
  },
  name: 'HomePage'
}
</script>

<style scoped>
.profile-img {
  max-width: 300px; /* Adjust as needed */
  border-radius: 2%; /* Makes the image round */
  /* Add object-fit to ensure the image covers the area without distortion */
  object-fit: cover; 
}
</style>
