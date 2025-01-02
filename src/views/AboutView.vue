<template>
  <div class="list-container">
    <ul class="list">
      <li class="list-item" v-for="(item, index) in items" :key="index">
        <div class="content-wrapper" :class="{ reverse: index % 2 !== 0 }">
          <div class="icon">
            <img :src="item.icon" alt="icon" />
          </div>
          <div class="text-content">
            <h3>{{ item.title }}</h3>
            <p>{{ item.content }}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup>
import schoolIcon from '@/assets/school.svg';
import projectIcon from '@/assets/project-icon.svg';
import workIcon from '@/assets/work-icon.svg';
import academicIcon from '@/assets/academic-projects.svg';
import personalIcon from '@/assets/personal-projects.svg';

const items = [
  {
    icon: schoolIcon,
    title: "Education",
    content: "Currently studying a Bachelor of Engineering in Computer Science\
    in Nanyang Technological University! Expected Honours (Distinction)",
  },
  {
    icon: workIcon,
    title: "Internship Experience",
    content: `Joined as an AI application intern at HTX, responsible for model training,\
    prototyping, data collection and augmentation.`,
  },
  {
    icon: projectIcon,
    title: "Final Year Project",
    content: "Empirical study on Multi U-net Diffusion models. This is a project where\
    I experiment with using multiple U nets in the diffusion process. I will test the\
    model parameters, diffusion schedule and timesteps ratio between the models.",
  },
  {
    icon: academicIcon,
    title: "Academic Projects",
    content: "Built a PHP application, \
    developed a social media cycling application on Android Studio, \
    trained models for gender recognition for Adience Dataset ",
  },
  {
    icon: personalIcon,
    title: "Personal Projects",
    content: "Created an AI Powered Text suggesting Mobile App (and local server)\
    , Made an Account Manager app for personal use, Created this web portfolio,\
    Joined a kaggle competition on titanic survival prediction and achieved top 20%",
  },
];


</script>

<style scoped>
/* General styles */
.list-container {
  padding: 1rem;
}

.list {
  list-style: none;
  margin: 0;
  padding: 0;
}

.list-item {
  margin-bottom: 2rem;
}

.content-wrapper {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-direction: column; /* Default to vertical layout for smaller screens */
}

.icon img {
  width: 50px;
  height: 50px;
}

.text-content {
  text-align: center;
}

.text-content h3 {
  margin: 0 0 0.5rem;
}

.text-content p {
  margin: 0;
}

/* Styles for larger screens */
@media (min-width: 1024px) {
  .content-wrapper {
    flex-direction: row; /* Horizontal layout for larger screens */
  }

  .content-wrapper.reverse {
    flex-direction: row-reverse; /* Reverse layout for alternating items */
  }

  .text-content {
    text-align: left; /* Align left by default */
  }

  .content-wrapper.reverse .text-content {
    text-align: right; /* Align right for reversed items */
  }

  .icon img {
    width: 70px; /* Larger icons for larger screens */
    height: 70px;
  }
}
</style>
