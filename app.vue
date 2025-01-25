<template>
  <main class="container">
    <div id="resume" class="d-flex">
      <!-- Left Column -->
      <div class="left-col">
        <!-- Contact -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[1] }}</h4>
          <ul>
            <li>12345678</li>
            <li>mail@gmail.com</li>
            <li>Tunis Ariana, 9999 Place</li>
          </ul>
        </div>

        <!-- About Me -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[0] }}</h4>
          <div class="justified-text">{{ introText }}</div>
        </div>

        <!-- Skills -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[2] }}</h4>
          <div class="skill-category">
            <strong>Languages:</strong>
            <ul>
              <li v-for="(skill, index) in skills.languages" :key="index">{{ skill }}</li>
            </ul>
          </div>
          <div class="skill-category">
            <strong>Frameworks:</strong>
            <ul>
              <li v-for="(skill, index) in skills.frameworks" :key="index">{{ skill }}</li>
            </ul>
          </div>
          <div class="skill-category">
            <strong>Tools:</strong>
            <ul>
              <li v-for="(skill, index) in skills.tools" :key="index">{{ skill }}</li>
            </ul>
          </div>
        </div>

        <!-- Languages -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[3] }}</h4>
          <ul>
            <li>English: Fluent</li>
            <li>French: Intermediate</li>
          </ul>
        </div>
      </div>

      <!-- Right Column -->
      <div class="right-col">
        <!-- Name and Title -->
        <div class="personal-name">{{ name }}</div>
        <div class="personal-title">{{ title }}</div>

        <!-- Technical Interests -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[4] }}</h4>
          <ul>
            <li>Web Development (Frontend & Backend)</li>
            <li>Mobile App Development (Cross-Platform with React Native)</li>
          </ul>
        </div>

        <!-- Projects -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[5] }}</h4>
          <div v-for="(project, index) in projects" :key="index" class="project-item">
            <h5>{{ project.name }}</h5>
            <p class="justified-text">{{ project.description }}</p>
          </div>
        </div>

        <!-- Education -->
        <div class="resume-section">
          <h4 class="section-headline">{{ headlines[6] }}</h4>
          <div class="justified-text">
            <strong>2021 – Present:</strong> Bachelor’s Degree in Computer Science<br>
            Faculty of Sciences of Tunis (FST)<br>
            <em>Skills Developed:</em> Algorithms, Web and Mobile Development, Artificial Intelligence, Database Management
          </div>
          <div class="justified-text">
            <strong>2021:</strong> Technical Baccalaureate
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>

// Data
const name = 'Tej Eddine Benamor';
const title = 'Computer Science Student';
const introText = 'A motivated third-year computer science student at the Faculty of Sciences of Tunis (FST), skilled in web and mobile development. Passionate about building innovative solutions and eager to contribute to real-world projects during my internship.';
const headlines = [
  'About Me',
  'Contact',
  'Skills',
  'Languages',
  'Technical Interests',
  'Projects',
  'Education',
];
const skills = {
  languages: ['Java', 'Python', 'C', 'JavaScript', 'TypeScript'],
  frameworks: ['React', 'Vue.js', 'Nuxt.js', 'React Native (Expo)', 'Java Enterprise Edition (JEE)'],
  tools: ['MySQL', 'SQLite', 'Expo', 'Git', 'Maven'],
};
const projects = [
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
</style>