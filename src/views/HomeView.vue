<template>
  <div class="home">
    <HomePage/>
  </div>
</template>

<script>
// @ is an alias to /src
import HomePage from '@/components/HomeComponent.vue'

export default {
  name: 'HomeView',
  components: {
    HomePage
  }
}
</script>

<style scoped>
  .home{
  /* Use the full height of the viewport */
  min-height: 100vh;
  
  background-color: #212121;

  /* Set up the background image to cover the entire container */
  background-size: cover;
  
  /* Set the background image to be fixed in the viewport */
  background-attachment: fixed;
  
  /* Position the background image */
  background-position: center center;
  
  /* Ensure the image doesn't repeat */
  background-repeat: no-repeat;


}
</style>
