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
        <text class="styled-text">Of course, this isn't me...<br> Welcome to my portfolio app!</text>
      </div>
      

      <nav>
        <ul>
          <li>
            <RouterLink to="/">
              Home
            </RouterLink>
            <img src="@/assets/home.svg" alt="Home" class="icon" />
          </li>
          <li>
            <RouterLink to="/about">About</RouterLink>
            <img src="@/assets/profile-2.svg" alt="About" class="icon" />
          </li>

          <li>
            <RouterLink to="/projects">Projects</RouterLink>
            <img src="@/assets/folder.svg" alt="Projects" class="icon" />
          </li>

          <li>
            <RouterLink to="/interests">Interests</RouterLink>
            <img src="@/assets/music.svg" alt="Interests" class="icon" />
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



header {
  line-height: 1.5;
  max-height: 100vh;
}

.styled-text {
  font-size: 20px;
  color: green;

}

.doggo {
  max-height: 400px;
  border:5px solid green; /* Specifies width, style, and color */
  border-radius: 20px; /* add curves */
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  font-size: 20px;
  text-align: center;
  margin-top: 2rem;
  /* Add space to the right */
}

nav ul {
  display: flex;
  flex-direction: column;
  font-size:30px;
  padding: 0;
  margin: 0;
  list-style-type: none; /* Removes the default bullet points */
}

nav li {
  display: flex; /* Use flex to align RouterLink and image side by side */
  align-items: center; /* Vertically align the items */
  margin-bottom: 5rem; /* Add spacing between items */
}

nav .icon {
  width: 40px; /* Adjust the icon size */
  height: 40px; /* Adjust the icon size */
  margin-left: 0.5rem; /* Add space between text and icon */
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



@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right:60px;
    /* padding-right: calc(var(--section-gap) / 2); */
  }



  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    align-items: center; /* Vertically align the items */
    justify-content: space-between; /* Space out elements in the row */
    width: 100%; /* Ensure it takes full width */
  }

  nav {
    margin-top: 0; /* Remove margin-top to align it properly */
    margin-left: 2rem; /* Increase margin-left to push nav to the right */
    text-align: left;
  }

  nav a {
    display: inline-block;
    padding: 0 1rem; /* Adjust padding for better spacing */
    border-left: 1px solid var(--color-border);
  }

  nav a:first-of-type {
    border: 0;
  }
}
</style>
