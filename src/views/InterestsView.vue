<template>
  <div class="projects">
    <ul class="project-list">
      <li class="project-item" v-for="(item, index) in items" :key="index">
        <!-- Top Section: Icon + Title + Description -->
        <div class="project-header">
          <div class="project-icon">
            <img :src="item.icon" alt="Project Icon" />
          </div>
          <div class="project-details">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </div>

        <!-- Bottom Section: Video or Image -->
        <div class="project-media">
          <div v-if="item.videoUrl" class="project-video">
            <iframe
              :src="item.videoUrl"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
          <div v-if="item.image" class="project-image">
            <img :src="item.image" alt="Project Image" />
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import tromboneIcon from "@/assets/trombone.svg"
import booksIcon from "@/assets/academic-projects.svg"
import musicIcon from "@/assets/music-color.svg"

export default {
  data() {
    return {
      items: [
        {
          icon: tromboneIcon,
          title: 'Tromboneeee!',
          description: 'The instrument that brings me great experiences. Ever since 2014, I have been learning the instrument in\
          concert and symphonic bands. Met a lot of great people with great mindsets, people who genuinely had a passion for music,\
          and met likeminded individuals overseas when I had a chance! Below is the most recent Japan exchange NTU symphonic band had\
          with Kindai University, one of the top bands in Osaka!',
          videoUrl: 'https://www.youtube.com/embed/LmDL71CzTJs',
          
          image: "src/assets/japan_kindai.jpg",
        },
        {
          icon: musicIcon,
          title: 'Composing!',
          description: 'I have tried my hand in transcribing game music when i was younger, and recently I have picked up some skills\
          in Digital Audio Workbenches, hence I could compose simple songs with better quality! I have composed trombone quintets, a lofi music\
          and 2 pop songs',
          videoUrl: "https://www.youtube.com/embed/Dz7WtLStjrk",
          image: null,
        },
        {
          icon: booksIcon,
          title: 'Reading and writing!',
          description: 'I love medieval European fantasy, especially when mixed with ample of magic and mysteries like Harry Potter!\
          I have read countless webnovels, and my personal favourites are "Fake Saint of The Year", "Release that Witch"\
          ,"Overlord"',
          videoUrl: null,
          image: null,
        },
      ],
    };
  },
};
</script>

  
<style scoped>
.projects {
  height:100%;
  width:130%;
  padding: 2rem;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
}

.project-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.project-item {
  margin-bottom: 3rem;
  padding: 1.5rem;
  border: 1px solid #ccc;
  border-radius: 8px;
  background-color: #f9f9f9;
}

.project-header {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.project-icon img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
}

.project-details {
  flex: 1;
}

.project-details h3 {
  margin: 0;
  font-size: 1.5rem;
}

.project-details p {
  margin: 0.5rem 0 0;
  font-size: 1rem;
  color: #555;
}

.project-media {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1.5rem;
}

.project-video iframe,
.project-image img {
  width: 100%; /* Make them responsive */
  max-width: 500px; /* Set a fixed maximum width */
  aspect-ratio: 16 / 9; /* Maintain consistent aspect ratio */
  height: auto; /* Automatically calculate height based on width */
  border-radius: 8px; /* Add rounded corners */
  object-fit: cover; /* Ensure image/video fits nicely */
  border: 1px solid #ddd; /* Add a border */
}



/* Larger screens */
@media (min-width: 1024px) {
  .project-header {
    flex-direction: row; /* Horizontal layout for icon and details */
  }

  .project-media {
    flex-direction: row; /* Keep video/image side by side */
  }
}
</style>

  