<script setup>
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>

  <main class="introduction">
    Welcome to my portfolio app! This is a simple app built using vue.JS and Vite. <br><br>
    This will be part of a series of projects I will be doing within this semester to further upgrade myself with the necessary skills
    in software development.
  </main>
  <div class="profile-pic-container">
    <img src="@/assets/me.jpg" alt="profile pic home" class="profile-pic-home"/>
  </div>

</template>

<style>



.profile-pic-home {
  width: 70vw;  /* Adjust width dynamically based on the screen */
  height: 70vw; /* Ensure the image remains square */
  object-fit: cover; /* Ensure image covers the square area */
  border-radius: 50%; /* Make the profile picture circular */
}

@media (max-width: 768px){
  .introduction {
    display: flex;
    align-items: center;
    justify-content: center; /* Center text horizontally if needed */
    font-family:"Sour Gummy", "Garamond", 'Franklin Gothic', sans-serif;
    font-size: 25px;
    padding: 20px; /* Add some padding to ensure text doesn't touch edges */
    flex-direction: column; /* Make text stack vertically */
    /* margin-bottom: 5vw;  */
  }
  .profile-pic-container {
    display: flex;
    justify-content: center; /* Centers the image horizontally */
    align-items: center; /* Centers the image vertically */
    width: 100%; /* Ensure the container takes full width */
    height: 55vh; /* Adjust height as needed */
    margin-top: -10vw; 
  }  
}



@media (min-width: 768px) and (max-width: 1024px){
  .introduction {
    display: flex;
    align-items: center;
    justify-content: center; /* Center text horizontally if needed */
    font-family:"Sour Gummy", "Garamond", 'Franklin Gothic', sans-serif;
    font-size: 25px;
    padding: 20px; /* Add some padding to ensure text doesn't touch edges */
    flex-direction: column; /* Make text stack vertically */
    /* margin-bottom: 5vw;  */
  }
  .profile-pic-container {
    display: flex;
    justify-content: center; /* Centers the image horizontally */
    align-items: center; /* Centers the image vertically */
    width: 100%; /* Ensure the container takes full width */
    height: 55vh; /* Adjust height as needed */
    margin-top: 15vw; 
  }

}

@media (min-width: 1024px){
  .profile-pic-container{
    display: None;
  }
  .introduction {
    display: flex;
    justify-content: center; /* Centers the text horizontally */
    align-items: center; /* Centers the text vertically */
    font-family:"Sour Gummy", "Garamond", 'Franklin Gothic', sans-serif;
    font-size: 25px;
    padding: 20px;
    flex-direction: column; /* Ensures the text stays in a vertical layout */
    height: 100vh; /* Ensures the container takes full viewport height */
    text-align: center; /* Center the text content horizontally */
    margin-bottom: 5vw; /* Adds space below the introduction section */
  }


}
</style>

