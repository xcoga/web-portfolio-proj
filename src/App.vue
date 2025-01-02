<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>

  <header>

    
    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->
      <div>
        <img src="@/assets/doggo.jpg" alt="profile pic" class="doggo"/>
        <text class="styled-text">Welcome to my portfolio app!</text>
      </div>
      

      <nav>
        <ul>
          <li>
            <RouterLink to="/">
              Home
              <img src="@/assets/home.svg" alt="Home" class="icon" />
            </RouterLink>
            
          </li>
          <li>
            <RouterLink to="/about">
               About
              <img src="@/assets/profile-2.svg" alt="About" class="icon" />
            </RouterLink>
            
          </li>

          <li>
            <RouterLink to="/projects">
              Projects
              <img src="@/assets/folder.svg" alt="Projects" class="icon" />
            </RouterLink>
            
          </li>

          <li>
            <RouterLink to="/interests">
              Interests
              <img src="@/assets/music.svg" alt="Interests" class="icon" />
            </RouterLink>
            
          </li>

        </ul>
      </nav>
    </div>
  </header>

  <Transition name="fade" mode="out-in">
    <RouterView />
  </Transition>

  
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.styled-text {
  font-size: 20px;
  color: green;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (max-width: 1024px){
  .doggo {
    display: none;
  }
  .styled-text {
    display: none;
  }
  .icon {
    height: 2rem;
    width: auto;
  }

  router-view {
    display: block;
    padding: 20px;
    border-radius: 8px;
    max-width: fit-content;    
  }

  /* Make nav items appear in a row */
  nav ul {
    display: flex;
    flex-direction: row; /* Set flex direction to row for smaller screens */
    padding: 0;
    margin: 0;
    list-style-type: none; /* Remove bullet points */
    justify-content: center; /* Center the items horizontally */
  }

  nav li {
    display: inline-block; /* Align items in a row */
    margin-right: 2rem; /* Add spacing between items */
  }

  /* Optional: Adjust icon size for smaller screens */
  nav .icon {
    width: 30px;
    height: 30px;
    margin-left: 0.5rem;
  }
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: 60px;
  }

  .doggo {
    max-height: 400px;
    border: 5px solid green;
    border-radius: 20px;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }

  nav {
    font-size: 20px;
    text-align: center;
    margin-top: 2rem;
  }

  nav ul {
    display: flex;
    flex-direction: column;
    font-size: 30px;
    padding: 0;
    margin: 0;
    list-style-type: none;
  }

  nav li {
    display: flex;
    align-items: center;
    margin-bottom: 5rem;
  }

  nav .icon {
    width: 40px;
    height: 40px;
    margin-left: 0.5rem;
  }

  nav a.router-link-exact-active {
    color: var(--color-text);
  }

  nav a.router-link-exact-active:hover {
    background-color: transparent;
  }

  nav a {
    display: inline-block;
    padding: 0 2rem;
    border-left: 1px solid var(--color-border);
  }

  nav a:first-of-type {
    border: 0;
  }
}
</style>

