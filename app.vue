<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <!-- Left Column -->
      <div class="left-col">
        <!-- Contact -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 0)">
            {{ headlines[0] }}
          </h4>
          <ul >
            <li contenteditable="true" data-key="contact.phone" @input="updateProperty">{{ contact.phone }}</li>
            <li contenteditable="true" data-key="contact.email" @input="updateProperty">{{ contact.email }}</li>
            <li contenteditable="true" data-key="contact.address" @input="updateProperty">{{ contact.address }}</li>
          </ul>
        </div>

        <!-- About Me -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 1)">
            {{ headlines[1] }}
          </h4>
          <div contenteditable="true" data-key="introText" @input="updateProperty">{{ introText }}</div>
        </div>

        <!-- Skills -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 2)">
            {{ headlines[2] }}
          </h4>
          <div class="skill-category">
            <strong>{{ headlines[3] }}</strong>
            <ul>
              <li v-for="(skill, index) in skills.languages" :key="index" contenteditable="true" data-key="skills" @input="updateProperty">{{ skill }}</li>
            </ul>
          </div>
          <div class="skill-category">
            <strong>{{ headlines[4] }}</strong>
            <ul>
              <li v-for="(skill, index) in skills.frameworks" :key="index" contenteditable="true" data-key="skills" @input="updateProperty">{{ skill }}</li>
            </ul>
          </div>
          <div class="skill-category">
            <strong>{{ headlines[5] }}</strong>
            <ul>
              <li v-for="(skill, index) in skills.tools" :key="index" contenteditable="true" data-key="skills" @input="updateProperty">{{ skill }}</li>
            </ul>
          </div>
        </div>

        <!-- Languages -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 6)">
            {{ headlines[6] }}
          </h4>
          <ul>
            <li
                v-for="(language, index) in languages"
                :key="index"
                contenteditable="true"
                :data-key="`languages.${index}.name`"
                @input="updateProperty"
                >
              {{ language.name }}: {{ language.level }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Right Column -->
      <div class="right-col">
        <!-- Name and Title -->
        <div class="personal-name" contenteditable="true" data-key="name" @input="updateProperty">{{ name }}</div>
        <div class="personal-title" contenteditable="true" data-key="title" @input="updateProperty">{{ title }}</div>

        <!-- Technical Interests -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 7)">
            {{ headlines[7] }}
          </h4>
          <ul>
          <li
            v-for="(interest, index) in technicalInterests"
            :key="index"
            contenteditable="true"
            :data-key="`technicalInterests.${index}`"
            @input="updateProperty"
          >
      {{ interest }}
    </li>
          </ul>
        </div>

        <!-- Projects -->
        <div class="resume-section">
          <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 8)">
            {{ headlines[8] }}
          </h4>
          <div v-for="(project, index) in mainProjects" :key="index" class="project-item" contenteditable="true"
                :data-key="`languages.${index}.name`"
                @input="updateProperty">
            <h5>{{ project.name }}</h5>
            <p class="justified-text">{{ project.description }}</p>
          </div>

          <!-- Other Projects -->
          <div class="other-projects">
            <h6>Other Projects:</h6>
            <ul>
              <li v-for="(project, index) in otherProjects" :key="index" class="other-project-item" contenteditable="true"
                :data-key="`languages.${index}.name`"
                @input="updateProperty">
                <strong>{{ project.name }}:</strong> {{ project.description }}
              </li>
            </ul>
          </div>
        </div>

        <!-- Education -->
        <div class="resume-section">
  <h4 class="section-headline" contenteditable="true" @input="updateHeadline($event, 9)">
    {{ headlines[9] }}
  </h4>
  <div v-for="(edu, index) in education" :key="index" class="justified-text">
            <strong
            contenteditable="true"
            :data-key="`education.${index}.period`"
            @input="updateProperty"
            >
              {{ edu.period }}:
            </strong>
            <span
              contenteditable="true"
              :data-key="`education.${index}.degree`"
              @input="updateProperty"
            >
              {{ edu.degree }}
            </span>
            <br />
            <span
              contenteditable="true"
              :data-key="`education.${index}.institution`"
              @input="updateProperty"
            >
            {{ edu.institution }}
          </span>
          <br />
            <em
              contenteditable="true"
              :data-key="`education.${index}.skills`"
              @input="updateProperty"
            >
              {{ edu.skills }}
            </em>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue';

// Data
const name = 'Tej Eddine Benamor';
const title = 'Computer Science Student';
const introText = 'A motivated third-year computer science student at the Faculty of Sciences of Tunis (FST), skilled in web and mobile development. Passionate about building innovative solutions and eager to contribute to real-world projects during my internship.';

const contact = ref({
  phone: '12345678',
  email: 'mail@gmail.com',
  address: 'Tunis Ariana, 9999 Place',
});

// Make headlines reactive
const headlines = ref([
  'Contact',
  'About Me',
  'Skills',
  'Languages',
  'Frameworks',
  'Tools',
  'Languages',
  'Technical Interests',
  'Projects',
  'Education',
]);

const skills = {
  languages: ['Java', 'Python', 'C', 'TypeScript'],
  frameworks: ['React', 'Vue.js', 'Nuxt.js', 'React Native (Expo)', 'Java Enterprise Edition (JEE)'],
  tools: ['MySQL', 'SQLite', 'Expo', 'Git', 'Maven'],
};
const languages = ref([
  { name: 'English', level: 'Fluent' },
  { name: 'French', level: 'Intermediate' },
]);

const technicalInterests = ref([
  'Web Development (Frontend & Backend)',
  'Mobile App Development (Cross-Platform with React Native)',
]);

const mainProjects = [
  {
    name: 'Resume Builder with Nuxt.js',
    description: 'Built a dynamic resume builder application using Nuxt.js for seamless server-side rendering. Enabled users to create, edit, and export professional resumes in PDF format.',
  },
  {
    name: 'Carpooling System Backend (Java Enterprise Edition - JEE)',
    description: 'Collaborated with a team of three to develop the backend for a carpooling application. Implemented core functionalities such as user management, ride allocation, and payment integration.',
  },
  {
    name: 'Library Management System (React Native & Prisma)',
    description: 'Developed a mobile application for library management using React Native (Expo) and Prisma as the ORM. Features included book tracking, user management, and real-time updates.',
  },
];

const otherProjects = [
  {
    name: 'Library Management System (Java)',
    description: 'A desktop application for library management.',
  },
  {
    name: 'Car Allocation System (C)',
    description: 'A car allocation system built with C.',
  },
  {
    name: '8 Puzzle with Python (AI)',
    description: 'Implemented the 8-puzzle problem using Python with AI algorithms.',
  },
];

// Method to update headlines
const updateHeadline = (event, index) => {
  headlines.value[index] = event.target.innerText;
};
const updateProperty = (event) => {
  const key = event.target.dataset.key; // Get the key from the data attribute
  const keys = key.split('.'); // Split the key into parts

  // Traverse the data structure to find the target property
  let target = value; // Assuming `value` is your reactive data object
  for (let i = 0; i < keys.length - 1; i++) {
    target = target[keys[i]];
  }

  // Update the target property with the new value
  target[keys[keys.length - 1]] = event.target.innerText;
};
const education = ref([
  {
    period: '2021 – Present',
    degree: 'Bachelor’s Degree in Computer Science',
    institution: 'Faculty of Sciences of Tunis (FST)',
    skills: 'Algorithms, Web and Mobile Development, Artificial Intelligence, Database Management',
  },
  {
    period: '2021',
    degree: 'Technical Baccalaureate',
    institution: '', // Add institution if applicable
    skills: '', // Add skills if applicable
  },
]);

</script>


<style scoped>
#resume {
  box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
  height: 297mm;
  width: 210mm;
  display: flex;
}

.left-col {
  background-color: var(--background-color-left);
  color: var(--text-color-left);
  border-right: 1px solid var(--highlight-color-left);
  width: 30%;
  padding: 30px;
}

.right-col {
  background-color: var(--background-color-right);
  color: var(--text-color-right);
  width: 70%;
  padding: 30px;
}

.section-headline {
  font-size: 20px;
  font-weight: var(--headline-weight);
  margin-bottom: 15px;
  margin-top: 0;
}

.right-col .section-headline {
  color: var(--highlight-color-right);
}

.left-col .section-headline {
  border-bottom: 1px solid var(--highlight-color-left);
  padding-bottom: 5px;
  margin-right: -30px;
  padding-right: 10px;
  color: var(--highlight-color-left);
}

.resume-section {
  margin-bottom: 30px;
}

.personal-name {
  font-size: 28px;
  font-weight: bold;
  margin-bottom: 5px;
}

.personal-title {
  font-size: 18px;
  color: var(--highlight-color-right);
  margin-bottom: 20px;
}

.project-item {
  margin-bottom: 20px;
}

.project-item h5 {
  margin: 0;
  font-size: 18px;
  color: var(--highlight-color-right);
}

.project-item p {
  margin: 5px 0 0 0;
  font-size: 14px;
}

.justified-text {
  text-align: justify;
}

.skill-category {
  margin-bottom: 15px;
}

.skill-category strong {
  display: block;
  margin-bottom: 5px;
  color: var(--highlight-color-left);
}

.other-projects {
  margin-top: 20px;
}

.other-projects h6 {
  font-size: 16px;
  color: var(--highlight-color-right);
  margin-bottom: 10px;
}

.other-project-item {
  font-size: 13px;
  margin-bottom: 5px;
}
</style>