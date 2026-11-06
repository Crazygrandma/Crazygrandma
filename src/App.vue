<script setup lang="ts">

import SkillItem from './components/SkillItem.vue'

interface Skill {
  name: string
  projectCount: number
}

const skills: Record<string, Skill[]> = {
  Languages: [
    { name: 'Python', projectCount: 10 },
    { name: 'Java', projectCount: 0 },
    { name: 'C', projectCount: 0 },
    { name: 'JavaScript', projectCount: 0 },
    { name: 'TypeScript', projectCount: 0 },
    { name: 'C++', projectCount: 1 },
    { name: 'C#', projectCount: 0 },
  ],

  'Frameworks & Libraries': [
    { name: 'React.js', projectCount: 0 },
    { name: 'Vue.js', projectCount: 0 },
    { name: 'Express.js', projectCount: 0 },
    { name: 'FastAPI', projectCount: 0 },
    { name: 'Three.js', projectCount: 0 },
    { name: 'wlroots', projectCount: 0 },
  ],

  Architectures: [
    { name: 'Client-Server', projectCount: 0 },
    { name: 'MVC', projectCount: 0 },
  ],

  Systems: [
    { name: 'Wayland', projectCount: 0 },
    { name: 'Linux', projectCount: 0 },
    { name: 'Git', projectCount: 0 },
  ],
}

import ThreeScene from './components/ThreeScene.vue'

const projects = [
  {
    title: 'Wayterra',
    description: 'An experimental desktop environment inspired by Terraria.'
  },
  {
    title: 'Project Two',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
  },
  {
    title: 'Project Three',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.'
  }
]

const socials = [
  { name: 'GitHub', url: 'https://github.com/' },
  { name: 'LinkedIn', url: 'https://linkedin.com/' },
  { name: 'Email', url: 'mailto:your@email.com' }
]
</script>

<template>
  <main>
    <!-- About -->
<section id="about" class="section about">
  <div class="intro">
    <div class="profile-image">
      <img src="/profile.jpg" alt="Profile picture" />
    </div>

    <div class="intro-text">
      <p class="eyebrow">SOFTWARE DEVELOPER</p>
      <h1>Henry Zöllner</h1>
      <p class="subtitle">
        Creative software developer driven by curiosity,
        experimentation, and the desire to understand how things work.
      </p>
    </div>
  </div>

  <div class="about-description">
    <h2>A little about me</h2>
    <p>
      I enjoy exploring unfamiliar technologies, experimenting with ideas, 
      and connecting concepts from different fields to create something new.
      When something catches my interest, I dive deep into its
      fundamentals, often challenging myself with projects that
      initially seem beyond my capabilities. For me, every challenge
      is an opportunity to learn something new and expand what I can build.
    </p>
  </div>
</section>

    <!-- Projects -->
    <!-- <section id="projects" class="section">
      <div class="section-heading">
        <p class="eyebrow">WHAT I'VE BEEN WORKING ON</p>
 
        <h2>Projects</h2>
      </div>

      <div class="projects-grid">
        <div
          v-for="project in projects"
          :key="project.title"
          class="project-card"
        >
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </div>
      </div>
    </section> -->

    <!-- Skills -->
    <!-- <section id="skills" class="section">
      <div class="section-heading">
        <p class="eyebrow">MY TOOLBOX</p>
        <h2>Skills & Technologies</h2>
      </div>


      <div class="skills-grid">
        <div
          v-for="(items, category) in skills"
          :key="category"
          class="skill-category"
        >
          <h3>{{ category }}</h3>

          <div class="skill-list">
            <SkillItem
              v-for="skill in items"
              :key="skill.name"
              :name="skill.name"
              :project-count="skill.projectCount"
            />
          </div>
        </div>
      </div>


      Three.js visualization
      <div class="skills-visualization">
        <h3>My Technical Landscape</h3>
        <p class="visualization-description">
          An interactive visualization of my skills and technologies.
        </p>

        <div class="three-scene">
          <ThreeScene />
        </div>
      </div>
    </section> -->

    <!-- Socials
    <section id="socials" class="section socials">
      <div class="section-heading">
        <p class="eyebrow">GET IN TOUCH</p>
        <h2>Find me online</h2>
      </div>

      <div class="social-links">
        <a
          v-for="social in socials"
          :key="social.name"
          :href="social.url"
          target="_blank"
          rel="noopener noreferrer"
        >
          {{ social.name }}
          <span>↗</span>
        </a>
      </div>
    </section> -->

    <!-- Footer -->
    <footer class="footer"></footer>
  </main>
</template>

<style>
:root {
  font-family: Inter, system-ui, sans-serif;
  color: #e5e7eb;
  background: #111318;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  min-width: 320px;
}

main {
  width: 100%;
}

.section {
  max-width: 1100px;
  margin: 0 auto;
  padding: 100px 32px;
  border-bottom: 1px solid #292d35;
}

.about {
  padding-top: 120px;
}

.intro {
  display: flex;
  align-items: center;
  gap: 56px;
}

.profile-image {
  width: 240px;
  height: 240px;
  flex-shrink: 0;
  overflow: hidden;
  border-radius: 12px;
  background: #292d35;
}

.profile-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.intro-text {
  max-width: 600px;
}

.eyebrow {
  color: #8b9bb4;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.15em;
}

h1 {
  font-size: clamp(2.5rem, 6vw, 4rem);
  margin: 16px 0;
  letter-spacing: -0.04em;
}

h2 {
  font-size: 2rem;
  letter-spacing: -0.03em;
}

h3 {
  font-size: 1.15rem;
}

.subtitle {
  color: #a1a7b3;
  font-size: 1.1rem;
  line-height: 1.7;
}

.about-description {
  max-width: 750px;
  margin: 90px auto 0;
  text-align: center;
}

.about-description p {
  color: #a1a7b3;
  font-size: 1.05rem;
  line-height: 1.9;
}

.section-heading {
  margin-bottom: 40px;
}

.section-heading h2 {
  margin-top: 12px;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.project-card {
  min-height: 180px;
  padding: 24px;
  background: #191c23;
  border: 1px solid #292d35;
  border-radius: 8px;
  transition: border-color 0.2s;
}

.project-card:hover {
  border-color: #657b9d;
}

.project-card p {
  color: #a1a7b3;
  line-height: 1.6;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.skill-category h3 {
  margin-bottom: 18px;
}

.skill-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.skill-tag {
  padding: 9px 13px;
  color: #c6d0df;
  background: #191c23;
  border: 1px solid #292d35;
  border-radius: 5px;
  font-size: 0.9rem;
}

.skills-visualization {
  margin-top: 80px;
  text-align: center;
}

.visualization-description {
  color: #a1a7b3;
}

.three-scene {
  width: 100%;
  height: 450px;
  margin-top: 30px;
  overflow: hidden;
  background: #191c23;
  border: 1px solid #292d35;
  border-radius: 8px;
}

.three-scene > * {
  width: 100%;
  height: 100%;
}

.social-links {
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
}

.social-links a {
  color: #c6d0df;
  text-decoration: none;
  transition: color 0.2s;
}

.social-links a:hover {
  color: white;
}

.social-links span {
  margin-left: 5px;
  color: #8b9bb4;
}

.footer {
  height: 100px;
  background: #191c23;
}

/* Responsive layout */
@media (max-width: 750px) {
  .section {
    padding: 70px 24px;
  }

  .intro {
    flex-direction: column;
    align-items: flex-start;
    gap: 30px;
  }

  .profile-image {
    width: 180px;
    height: 180px;
  }

  .projects-grid,
  .skills-grid {
    grid-template-columns: 1fr;
  }

  .about-description {
    margin-top: 60px;
  }

  .three-scene {
    height: 350px;
  }
}
</style>
