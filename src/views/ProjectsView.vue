<template>
  <div class="projects">
    <div class="content">
      <div class="scrollable-list">
        <!-- Render each project -->
        <div class="project-item" v-for="project in projects" :key="project.id">
          <h3>{{ project.title }}</h3>
          
          <!-- Render description with paragraphs -->
          <div v-html="formattedDescription(project.description)"></div>
          
          <!-- Image placeholder -->
          <div class="project-image" v-if="project.image">
            <img :src="project.image" alt="Project Image" />
          </div>
          
          <!-- YouTube video iframe -->
          <div class="project-video" v-if="project.videoUrl">
            <iframe
              :src="project.videoUrl"
              frameborder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowfullscreen
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          title: "Social Cycling Application",
          description: `This is an application developed using Android Studio and linked to Firebase as our backend.\
          This application allows users to create, delete, join cycling events, as well as track their calories burnt and past cycling events.\
          This was the first ever complete project that I had built as an academic project, so there were many things that I learnt.\
          For example: routing between different activities/screens, passing of data between components, communicating with the database.`,
          image: "",
          videoUrl: "https://www.youtube.com/embed/StElj-Q8nFg",
        },
        {
          id: 2,
          title: "AI-powered Text Suggesting Mobile App",
          description: `Mobile application developed using React Native library and Expo framework. The backend is using my local computer\
          to host the OCR, YOLO and LLM. The mobile application makes a HTTP request towards the server(my pc), sending a screenshot of the\
          chat into the server.

          1) Server will process the received screenshot using YOLO to extract each message from their message boxes.


          2) The messages are sorted in sequence, according to their y coordinate position in the image.


          3) The messages are further sorted by user according to their x coordinate position in the image.


          4) Then, the OCR will be employed to recognise the text in each message box.


          5) The messages will be compiled for each user and then sent into the LLM for its response.


          6) To improve LLM's responses to be more natural, RAG is deployed on a database of self-collected data of local conversations.


          7) The LLM will rate the user's response, give suggestions on how he can improve and give an example text to send to the other person.`,
          image: "",
          videoUrl: "https://www.youtube.com/embed/8kgTB9cs8B4",
        },
        {
          id: 3,
          title: "PHP web app Cyber Attack",
          description: `Created a php app with a routing vulnerability to replicate the Target Breach 2013.
          This php app allows users to upload and download files, as well as view files.
          The vulnerability arises from the lack of file management when viewing files.
          As such, a webshell attack can be performed by uploading a .php file containing the malicious code.`,
          image: "",
          videoUrl: "https://www.youtube.com/embed/BOAoSEzRuaY",
        },
        {
          id: 4,
          title: "Titanic Survival Prediction",
          description: `Goal of this competition is to find which passengers will survive based on the given data.
          Made use of a final ensemble of deep learning models, managed to achieve top 20% of the leaderboard.


          The data had a lot of strings, so there was a lot to do in the cleaning of data. The trickiest part of the dataset was that\
          some seemingly unimportant details do contribute to the survival rate of passengers. Hence, I had to reclean the dataset\
          multiple times because certain versions of of the cleaning caused loss of information.\


          For example, under the Name, there is the title of each passenger. Certain passengers also had second names.\
          Some examples include: Braund, Mr. Owen Harris and Futrelle, Mrs. Jacques Heath (Lily May Peel), Montvila, Rev. Juozas


          Under Ticket, certain tickets have alphabet prefixes. Examples include: STON/O2. 3101282, W./C. 6607\
          Including these details into the machine learning model yielded better predictions.
          

          This project has taught me to be more careful in the dataset preprocessing stage, to not lose out important features needed\
          to improve the machine learning model.`,
          image: "src/assets/titanic_kaggle_leaderboard.png",
          videoUrl: "",
        },

        {
          id: 5,
          title: "Account Manager App",
          description: `An android project for personal use! It was getting difficult to track my accounts, and since I used to have a phone\
          that could not access google services, I decided to create a smaller version replica of Samsung Pass on my phone!`,
          image: "",
          videoUrl: "https://www.youtube.com/embed/trzJMfDl2DQ",
        },


        
      ],
    };
  },
  methods: {
    // Method to format the description by turning new lines into <p> tags
    formattedDescription(description) {
      return description
        .split('\n\n')  // Split description at double line breaks
        .map(paragraph => `<p>${paragraph.trim()}</p>`)  // Wrap each paragraph in <p> tags
        .join('');
    },
  },
};
</script>

<style>
@media (min-width: 1025px){
  .projects {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    width: 100%; /* Adjusted width to 90% of viewport width for smaller screens */
    max-width: 100%; /* Ensure it doesn't overflow */
    height: auto; /* Adjust height dynamically */
    overflow-x: auto; /* Allow horizontal scrolling if content overflows */
    flex-direction: column; /* Stack items vertically for smaller screens */
  }
}

@media (max-width: 1024px) {
  /* Container for the projects section */
  .projects {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
    width: 90vw; /* Adjusted width to 90% of viewport width for smaller screens */
    max-width: 100%; /* Ensure it doesn't overflow */
    height: auto; /* Adjust height dynamically */
    overflow-x: auto; /* Allow horizontal scrolling if content overflows */
    flex-direction: column; /* Stack items vertically for smaller screens */
  }

  /* Content wrapper */
  .content {
    max-width: 100%;
    margin: 0 auto;
    line-height: 1.6;
  }

  /* Scrollable list container */
  .scrollable-list {
    max-height: 600px;
    overflow-y: auto;
    border-radius: 8px;
    padding: 10px;
  }

  /* Individual project item */
  .project-item {
    margin-bottom: 20px;
    min-height: 400px;
    max-height: none;
    padding: 20px;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    width: 100%; /* Ensure the items take full width of their container */
  }

  /* Project image */
  .project-image img {
    width: 100%;
    height: auto;
    border-radius: 5px;
    margin-bottom: 10px;
    object-fit: cover;
  }

  /* Project video */
  .project-video iframe {
    width: 100%;
    height: 300px;
    border-radius: 5px;
    margin-top: 10px;
  }

  /* Optional: Adjust the margin-bottom of the project items for smaller screens */
  .project-item {
    margin-bottom: 15px;
  }
}


/* Content wrapper */
.content {
  max-width: 100%; /* Increased max width */
  margin: 0 auto;
  line-height: 1.6;
}

/* Scrollable list container */
.scrollable-list {
  max-height: 600px; /* Increased height */
  overflow-y: auto;
  /* border: 1px solid #ccc; */
  border-radius: 8px;
  padding: 10px;
  /* background-color: #f9f9f9; */
}

/* Individual project item */
.project-item {
  margin-bottom: 30px;
  min-height: 400px;
  max-height: none;
  /* max-height: 900px; */
  padding: 20px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 5px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* Project image */
.project-image img {
  width: 100%; /* Increased width to match container */
  height: auto; /* Maintain the aspect ratio */
  border-radius: 5px;
  margin-bottom: 10px;
  object-fit: cover; /* or 'contain' depending on the desired effect */
}

/* Project video */
.project-video iframe {
  width: 100%; /* Increased width to match container */
  height: 300px; /* Increased height for better visibility */
  border-radius: 5px;
  margin-top: 10px;
}

/* Add some hover effect to project items */
.project-item:hover {
  background-color: #f1f1f1;
  transform: translateY(-2px);
  transition: 0.3s ease-in-out;
}
</style>
