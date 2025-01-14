<script setup>
import { onMounted } from 'vue';
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

// onMounted(() => {
//   const videoElement = document.querySelector('video');
//   if (videoElement) {
//     videoElement.play();
//   }
// });
</script>

<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Lavishly+Yours&family=Sour+Gummy:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

  <!-- Background Video -->
  <div class="video-container">
    <video autoplay loop muted playsinline width="100%" height="100%" style="object-fit: cover;">
    <source src="@/assets/background_video.mp4" type="video/mp4" />
    </video>
  </div>

  <header>
    <div class="wrapper">
      <!-- <HelloWorld msg="You did it!" /> -->
      <div>
        <img src="@/assets/me.jpg" alt="profile pic" class="profile-pic"/>
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
    <RouterView class="router-view"/>
  </Transition>
</template>

<style scoped>
/* Background Video Styling */
.video-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  pointer-events: none;
  z-index: -1;
}

.video-container iframe {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100vw;
  height: 56.25vw; /* 16:9 Aspect Ratio */
  min-height: 100vh;
  min-width: 177.77vh; /* 16:9 Aspect Ratio */
  transform: translate(-50%, -50%);
}

.video-container video {
  opacity: 0.7; /* Adjust this value as needed */
}

.router-view {
  font-family: "Sour Gummy", serif;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 2s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.styled-text {
  font-size: 40px;
  font-family: "Lavishly Yours", serif;
  color: green;
}

@media (max-width: 1024px) {
  .profile-pic {
    display: none;
  }
  .styled-text {
    display: none;
  }
  .icon {
    height: 2rem;
    width: auto;
  }
  
  nav ul {
    display: flex;
    flex-direction: row;
    padding: 0;
    margin: 0;
    list-style-type: none;
    justify-content: center;
  }

  nav li {
    display: inline-block;
    margin-right: 2rem;
  }

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

  .profile-pic {
    width: 400px;
    height: 400px;
    border: 5px solid green;
    border-radius: 20px;
    object-fit: cover;
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
}
</style>
