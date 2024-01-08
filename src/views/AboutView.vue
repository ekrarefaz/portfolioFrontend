<template>
  <div class="about">
    <AboutPageComponent/>
  </div>
</template>

<script>
  import AboutPageComponent from '@/components/AboutComponents/AboutPageComponent.vue' 
  export default{
    data(){
      return{
        
      }
    },
    components:{
      AboutPageComponent,
    }
  }
</script>


<style scoped>
  .about{
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

