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
    title: 'DiscordGPTBot',
    description: 'A discord bot using pycord with local LLM support'
  },
  {
    title: 'CinematicCam',
    description: 'A camera mod for RocketLeague'
  }
]

const socials = [
  { name: 'GitHub', url: 'https://github.com/Crazygrandma' },
  //{ name: 'LinkedIn', url: 'https://linkedin.com/' },
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
    <h2>About me</h2>
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
    <section id="projects" class="section">
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
    </section>

    <!-- Skills -->
    <section id="skills" class="section">
      <!--<div class="section-heading">
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
      </div> -->


      <div class="skills-visualization">
        <div class="three-scene">
          <ThreeScene />
        </div>
      </div>
    </section>

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

<style src="./assets/App.css"></style>
