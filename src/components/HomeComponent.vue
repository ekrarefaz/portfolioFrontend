<template>
  <v-container>
    <v-row>
      <v-col cols="12" md="6" class="text-md-left text-center align-self-center">
        <!-- Your text content -->
        <h1>{{ currentGreeting }}</h1>
        <h2>I'm Ekrar Efaz</h2>
        <p>Welcome to my digital domain, where passion for Cyber-Security and mastery in Computer Science converge.</p>
        <div class="home-btn">
          <!-- LinkedIn Button -->
          <a :href="linkedinUrl" target="_blank">
            <v-btn  dark>
              <v-icon left>mdi-linkedin</v-icon>
              LinkedIn
            </v-btn>
          </a>        
          <router-link :to="{ name: 'about' }">
            <v-btn dark>More about me</v-btn>
          </router-link>
        </div>

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
      linkedinUrl: 'https://www.linkedin.com/in/secureekrarefaz/',
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
      currentGreeting: '',
      fullGreeting: 'Hello',
      greetingIndex: 0,
      interval: null,
      typingSpeed: 150,
    }
  },
  methods: {
    changeGreeting() {
      clearInterval(this.interval);
      this.greetingIndex = (this.greetingIndex + 1) % this.greetings.length;
      this.fullGreeting = this.greetings[this.greetingIndex];
      this.currentGreeting = '';
      this.typeGreeting(0);
    },
    typeGreeting(index) {
      if (index < this.fullGreeting.length) {
        this.currentGreeting += this.fullGreeting[index];
        setTimeout(() => this.typeGreeting(index + 1), this.typingSpeed);
      } else {
        this.interval = setInterval(this.changeGreeting, 4000); // Change greeting every 4 seconds
      }
    },
  },
  mounted() {
    this.typeGreeting(0);
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
.home-btn{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 45%;
  margin-top: 20px;
}
</style>
