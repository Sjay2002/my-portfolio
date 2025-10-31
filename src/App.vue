<template>
  <v-app class="portfolio-app">
    <!-- Navigation Bar -->
    <v-app-bar
      fixed
      class="navbar"
      :style="{ background: 'linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%)' }"
      elevation="4"
    >
      <v-container class="d-flex align-center justify-space-between">
        <div class="logo font-weight-bold text-h6" style="color: #0AB6BC">
          SJ
        </div>

        <!-- mobile menu button (hidden on desktop) -->
        <v-app-bar-nav-icon class="mobile-menu-button" @click="drawer = !drawer" />

        <v-spacer></v-spacer>
        <div class="nav-links d-flex gap-4">
          <a href="#home" class="nav-link">Home</a>
          <a href="#about" class="nav-link">About</a>
          <a href="#projects" class="nav-link">Projects</a>
          <a href="#skills" class="nav-link">Skills</a>
          <a href="#education" class="nav-link">Education</a>
          <a href="#contact" class="nav-link">Contact</a>
        </div>
      </v-container>
    </v-app-bar>

    <!-- Hero Section (split layout like reference) -->
    <section id="home" class="hero-section hero-split">
      <v-container fluid>
        <v-row class="align-center" style="min-height: 88vh">
          <v-col cols="12" md="6" class="hero-left">
            <h1 class="hero-title">Hi, I'm <span class="hero-name">Sithumini Jayasekara</span></h1>
            <!-- <p class="hero-subtitle">Full-Stack Developer</p> -->
            <!-- tagline separated so we can style it with a different font -->
            <p class="hero-tagline">Aspiring Software Engineer | Full-Stack Developer | Cloud Enthusiast</p>
            <p class="hero-lead">I’m a third-year IT undergraduate at the University of Moratuwa with a passion for creating efficient, scalable, and user-focused software solutions that drive real impact.</p>

            <div class="hero-ctas">
              <div class="cta-buttons">
                <a :href="cvPdf" download style="text-decoration: none">
                  <v-btn class="btn-primary" large>Download CV</v-btn>
                </a>
                <v-btn class="btn-outline" large href="#contact">Get In Touch</v-btn>
              </div>

              <!-- Hero contact icons (replicated from footer, colorful) -->
              <!-- moved below buttons and styled as lighter boxes -->
              <div class="hero-contacts mt-4 d-flex align-center">
                <a href="mailto:sithuminijayasekara6@gmail.com" class="hero-contact" title="Email">
                  <Icon icon="mdi:email" width="26" height="26" style="color:#EA4335" />
                </a>
                <a href="tel:+94713448461" class="hero-contact" title="Phone">
                  <Icon icon="mdi:phone" width="26" height="26" style="color:#34A853" />
                </a>
                <a href="https://www.linkedin.com" target="_blank" class="hero-contact" title="LinkedIn">
                  <Icon icon="logos:linkedin" width="26" height="26" style="color:#0A66C2" />
                </a>
                <a href="https://github.com/Sjay2002" target="_blank" class="hero-contact" title="GitHub">
                  <Icon icon="logos:github-icon" width="26" height="26" style="color:#181717" />
                </a>
                <a href="https://www.figma.com/@sjay2" target="_blank" class="hero-contact" title="Figma">
                  <img :src="figmaContact" alt="Figma" class="hero-contact-img" />
                </a>
              </div>
            </div>
          </v-col>

          <v-col cols="12" md="6" class="hero-right d-flex justify-center">
            <div class="hero-image">
              <img :src="profileImg" alt="profile" />
              <div class="hero-image-overlay"></div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <!-- Mobile navigation drawer (temporary) -->
    <v-navigation-drawer v-model="drawer" temporary class="mobile-drawer">
      <v-list>
        <v-list-item @click="drawer = false">
          <a href="#home" class="drawer-link">Home</a>
        </v-list-item>
        <v-list-item @click="drawer = false">
          <a href="#about" class="drawer-link">About</a>
        </v-list-item>
        <v-list-item @click="drawer = false">
          <a href="#projects" class="drawer-link">Projects</a>
        </v-list-item>
        <v-list-item @click="drawer = false">
          <a href="#skills" class="drawer-link">Skills</a>
        </v-list-item>
        <v-list-item @click="drawer = false">
          <a href="#education" class="drawer-link">Education</a>
        </v-list-item>
        <v-list-item @click="drawer = false">
          <a href="#contact" class="drawer-link">Contact</a>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

  <!-- About Section -->
  <section id="about" class="about-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-8 text-center" style="color: #0AB6BC">
          About Me
        </h2>

        <div class="about-cards">
          <div class="about-card profile-card">
            <h3 class="about-card-title">Profile</h3>
            <div class="about-card-body">
              <p>
                
              </p>
I’m an enthusiastic software engineering undergraduate at the University of Moratuwa with a strong interest in full-stack development. I enjoy building intuitive and scalable web applications using technologies such as React.js, Node.js, and Express. Through academic projects and self-driven learning, I’ve developed a solid understanding of both frontend and backend development practices. I’m eager to apply my technical skills, creativity, and problem-solving mindset to real-world projects and continue growing as a developer in dynamic, collaborative environments.
              <p>
                I enjoy collaborating with teams to deliver high-quality software solutions while embracing creativity and innovation. Passionate about continuous learning, I explore new technologies and best practices to sharpen my skills and make a meaningful impact through technology.
              </p>
            </div>
          </div>

          <div class="about-card contact-card">
            <h3 class="about-card-title">Contact Information</h3>
            <div class="about-card-body">
              <ul class="contact-list">
                <li>
                  <a href="mailto:sithuminijayasekara6@gmail.com" class="contact-icon-link" title="Email">
                    <v-icon class="contact-icon" small>mdi-email</v-icon>
                  </a>
                  <div>
                    <div class="contact-label">Email</div>
                    <a href="mailto:sithuminijayasekara6@gmail.com" class="contact-link">sithuminijayasekara6@gmail.com</a>
                  </div>
                </li>
                <li>
                  <a href="tel:+94713448461" class="contact-icon-link" title="Phone">
                    <v-icon class="contact-icon" small>mdi-phone</v-icon>
                  </a>
                  <div>
                    <div class="contact-label">Phone</div>
                    <a href="tel:+94713448461" class="contact-link">+94 (71) 344 8461</a>
                  </div>
                </li>
                <li>
                  <a href="https://www.linkedin.com" target="_blank" class="contact-icon-link" title="LinkedIn">
                    <v-icon class="contact-icon" small>mdi-linkedin</v-icon>
                  </a>
                  <div>
                    <div class="contact-label">LinkedIn</div>
                    <a href="https://www.linkedin.com" target="_blank" class="contact-link">Sithumini Jayasekara</a>
                  </div>
                </li>
                <li>
                  <a href="https://github.com/Sjay2002" target="_blank" class="contact-icon-link" title="GitHub">
                    <v-icon class="contact-icon" small>mdi-github</v-icon>
                  </a>
                  <div>
                    <div class="contact-label">GitHub</div>
                    <a href="https://github.com/Sjay2002" target="_blank" class="contact-link">Sjay2002</a>
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>

      </v-container>
    </section>

    <!-- Education Section -->
  <section id="education" class="education-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Education
        </h2>
        <div class="timeline-wrapper">
          <div class="timeline-list">
            <div class="timeline-item" v-for="edu in education" :key="edu.id">
              <div class="timeline-logo">
                <img
                  v-if="edu.logo"
                  :src="edu.logo"
                  :alt="edu.institution"
                  :class="{ 'logo-white-bg': edu.institution && /nibm/i.test(edu.institution) }"
                />
                <div v-else class="timeline-logo-fallback"></div>
              </div>
              <div class="timeline-content">
                <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
                  <v-card-text>
                    <h3 style="color: #0AB6BC" class="font-weight-bold">{{ edu.degree }}</h3>
                    <p style="color: #d0d0d0" class="text-body2 mb-2">{{ edu.institution }}</p>
                    <p style="color: #0AB6BC" class="text-caption font-weight-bold">{{ edu.period }}</p>
                    <p v-if="edu.details" style="color: #b0b0b0" class="text-body2 mt-2">{{ edu.details }}</p>
                  </v-card-text>
                </v-card>
              </div>
            </div>
          </div>
        </div>
      </v-container>
    </section>

  <!-- Projects Section -->
  <section id="projects" class="projects-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Featured Projects
        </h2>
        <v-row>
          <v-col v-for="project in projects" :key="project.id" cols="12" md="6" lg="6">
            <v-card
              class="project-card h-100"
              style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC; transition: all 0.3s ease"
              @mouseenter="project.hover = true"
              @mouseleave="project.hover = false"
            >
              <v-card-text>
                <h3 style="color: #0AB6BC" class="font-weight-bold mb-3">{{ project.title }}</h3>
                <p style="color: #b0b0b0" class="text-body2 mb-4">{{ project.description }}</p>
                <div class="mb-4">
                  <p style="color: #0AB6BC" class="text-caption font-weight-bold mb-2">Technologies:</p>
                  <div class="project-techs d-flex flex-wrap gap-2">
                    <v-chip
                      v-for="tech in project.technologies"
                      :key="tech"
                      size="small"
                      style="background: rgba(10, 182, 188, 0.2); color: #0AB6BC"
                    >
                      {{ tech }}
                    </v-chip>
                  </div>
                </div>
                <v-btn
                  v-if="project.github"
                  size="small"
                  variant="text"
                  style="color: #0AB6BC"
                  :href="project.github"
                  target="_blank"
                >
                  View on GitHub →
                </v-btn>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

  <!-- Skills Section -->
  <section id="skills" class="skills-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Skills & Expertise
        </h2>
        <v-row>
          <v-col v-for="skillCategory in skillCategories" :key="skillCategory.category" cols="12">
            <v-card class="skill-card">
              <v-card-text>
                <h3 style="color: #0AB6BC" class="font-weight-bold mb-4">{{ skillCategory.category }}</h3>
                <div class="skill-grid">
                  <template v-for="(skill, idx) in skillCategory.skills" :key="skill">
                    <div class="skill-box" :style="{ animationDelay: `${idx * 80}ms` }">
                      <div class="skill-icon-wrap">
                        <!-- Prefer a local asset placed in src/assets/skill-icons/ (png/svg/jpg). If present, show it.
                             Otherwise fall back to Iconify mapping, then to generated badge. -->
                        <img
                          v-if="getLocalIcon(skill)"
                          :src="getLocalIcon(skill)"
                          class="skill-img-box"
                          :alt="skill"
                          :style="{ width: getIconSize(skill) + 'px', height: getIconSize(skill) + 'px' }"
                        />
                        <Icon
                          v-else-if="skillIconifyMap[skill]"
                          :icon="skillIconifyMap[skill]"
                          :width="getIconSize(skill)"
                          :height="getIconSize(skill)"
                          class="skill-svg-icon"
                          :style="{ color: getIconColor(skill) }"
                        />
                        <img
                          v-else
                          :src="getSkillIconUrl(skill)"
                          class="skill-img-box"
                          :alt="skill"
                          :style="{ width: getIconSize(skill) + 'px', height: getIconSize(skill) + 'px' }"
                        />
                      </div>
                      <div class="skill-label">{{ skill }}</div>
                    </div>
                  </template>
                </div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

  <!-- Education Section
  <section id="education" class="education-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Education
        </h2>
        <div class="timeline-wrapper">
          <div class="timeline-list">
            <div class="timeline-item" v-for="edu in education" :key="edu.id">
              <div class="timeline-logo">
                <img
                  v-if="edu.logo"
                  :src="edu.logo"
                  :alt="edu.institution"
                  :class="{ 'logo-white-bg': edu.institution && /nibm/i.test(edu.institution) }"
                />
                <div v-else class="timeline-logo-fallback"></div>
              </div>
              <div class="timeline-content">
                <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
                  <v-card-text>
                    <h3 style="color: #0AB6BC" class="font-weight-bold">{{ edu.degree }}</h3>
                    <p style="color: #d0d0d0" class="text-body2 mb-2">{{ edu.institution }}</p>
                    <p style="color: #0AB6BC" class="text-caption font-weight-bold">{{ edu.period }}</p>
                    <p v-if="edu.details" style="color: #b0b0b0" class="text-body2 mt-2">{{ edu.details }}</p>
                  </v-card-text>
                </v-card>
              </div>
            </div>
          </div>
        </div>
      </v-container>
    </section> -->

  <!-- Contact Section -->
  <section id="contact" class="contact-section py-16" style="background: transparent">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Get In Touch
        </h2>
        <v-row justify="center">
          <v-col cols="12" md="8">
            <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
              <v-card-text>
                <!-- <div class="text-center mb-8">
                  <p style="color: #d0d0d0" class="text-body1 mb-6">
                    Fill out the form below and we'll open your email client so you can send me a message directly.
                  </p>
                </div> -->

                <v-form @submit.prevent="sendEmail">
                  <v-row>
                    <v-col cols="12" md="6">
                      <v-text-field
                        class="light-field"
                        v-model="contactName"
                        label="Name"
                        placeholder="Your name"
                        required
                        density="comfortable"
                        color="#0AB6BC"
                      />
                    </v-col>
                    <v-col cols="12" md="6">
                      <v-text-field
                        class="light-field"
                        v-model="contactEmail"
                        label="Email"
                        placeholder="Your email"
                        type="email"
                        required
                        density="comfortable"
                        color="#0AB6BC"
                      />
                    </v-col>
                    <v-col cols="12">
                      <v-text-field
                        class="light-field"
                        v-model="contactSubject"
                        label="Subject"
                        placeholder="Subject"
                        density="comfortable"
                        color="#0AB6BC"
                      />
                    </v-col>
                    <v-col cols="12">
                      <v-textarea
                        class="light-field"
                        v-model="contactMessage"
                        label="Message"
                        placeholder="Your message"
                        rows="6"
                        required
                        density="comfortable"
                        color="#0AB6BC"
                      />
                    </v-col>
                  </v-row>

                    <div class="mt-6 text-center">
                    <v-btn
                      type="submit"
                      size="large"
                      style="background: linear-gradient(135deg, #0AB6BC, #045C43); color: white"
                      :loading="sending"
                    >
                      Send Message
                    </v-btn>
                  </div>
                </v-form>

                <!-- feedback snackbar -->
                <v-snackbar v-model="snackbarVisible" :timeout="3500" :color="snackbarColor">
                  {{ snackbarMessage }}
                </v-snackbar>

              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

  <!-- Footer -->
  <footer style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%); padding: 2rem 0">
      <v-container>
        <div class="text-center">
          <div class="footer-contacts d-flex justify-center gap-6 mb-4">
            <a href="mailto:sithuminijayasekara6@gmail.com" class="footer-icon hero-contact" title="Email">
              <Icon icon="mdi:email" width="20" height="20" style="color:#ffffff" />
            </a>
            <a href="tel:+94713448461" class="footer-icon hero-contact" title="Phone">
              <Icon icon="mdi:phone" width="20" height="20" style="color:#ffffff" />
            </a>
            <a href="https://www.linkedin.com" target="_blank" class="footer-icon hero-contact" title="LinkedIn">
              <Icon icon="logos:linkedin" width="20" height="20" style="color:#ffffff" />
            </a>
            <a href="https://github.com/Sjay2002" target="_blank" class="footer-icon hero-contact" title="GitHub">
              <Icon icon="logos:github-icon" width="20" height="20" style="color:#ffffff" />
            </a>
            <!-- Figma icon removed from footer per request -->
          </div>

          <p style="color: #b0b0b0" class="text-body2 mb-2">
            © 2025 Sithumini Jayasekara. All rights reserved.
          </p>
          <p style="color: #0AB6BC" class="text-caption">
            Designed & Built with Vue.js + Vuetify
          </p>
        </div>
      </v-container>
    </footer>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
// drawer state for mobile nav
const drawer = ref(false)
import profileImg from './assets/my.jpg'
import cvPdf from './assets/Sithumini JayasekaraSE.pdf'
import { Icon } from '@iconify/vue'
import figmaContact from './assets/figma.png'
// Explicit local overrides (imported directly to avoid any glob/case issues)
import vuetifyIcon from './assets/skill-icons/vuetify.png'
import expressIcon from './assets/skill-icons/express.png'


// Prefer official SVGs from simple-icons when available. We'll import a subset
// of commonly-used icons and map skill names to those icon objects. For skills
// without a matching simple-icon we continue to fall back to the generated
// badge SVGs implemented previously.
import {
  siReact,
  siVuedotjs,
  siTailwindcss,
  siFigma,
  siNodedotjs,
  siJavascript,
  siHtml5,
  siPython,
  siMongodb,
  siMysql,
  siFirebase,
  siGithub
} from 'simple-icons/icons'

const simpleMap = {
  'React.js': siReact,
  'Vue.js': siVuedotjs,
  'Tailwind CSS': siTailwindcss,
  Figma: siFigma,
  'Node.js': siNodedotjs,
  JavaScript: siJavascript,
  HTML: siHtml5,
  Python: siPython,
  MongoDB: siMongodb,
  MySQL: siMysql,
  Firebase: siFirebase,
  'Git/GitHub': siGithub
}


// Iconify mapping (collection:name). Iconify will load icons on demand.
const skillIconifyMap = {
  // Programming Languages
  Java: 'logos:java',
  'C': 'logos:c',
  Python: 'logos:python',
  JavaScript: 'logos:javascript',
  HTML: 'logos:html-5',
  CSS: 'logos:css-3',

  // Frontend
  'React.js': 'logos:react',
  'Vue.js': 'logos:vue',
  'Tailwind CSS': 'logos:tailwindcss',
  Vuetify: 'logos:vuetify',

  // Backend
  'Node.js': 'logos:nodejs',
  // Express intentionally omitted here so the code falls back to a visible
  // generated badge or a local SVG (preferred) instead of using a dark
  // monochrome simple/icon that can be hard to see on the theme.

  // Databases
  MySQL: 'logos:mysql',
  MongoDB: 'logos:mongodb',
  Firebase: 'logos:firebase',
  PostgreSQL: 'logos:postgresql',

  // Tools
  'Git/GitHub': 'logos:github-icon',
  Git: 'logos:git-icon',
  Figma: 'logos:figma',
  Docker: 'logos:docker-icon',
  AWS: 'logos:aws',
  VSCode: 'logos:visual-studio-code',
  Canva: 'logos:canva',
  Arduino: 'logos:arduino',
  'OpenAI API': 'logos:openai-icon'
}


function svgFromSimpleIcon(si) {
  if (!si || !si.svg) return null
  // simple-icons' `svg` property gives inner paths; wrap in svg element
  const svg = `<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' width='128' height='128' fill='%23${si.hex}'>${si.svg}</svg>`
  return `data:image/svg+xml;utf8,${encodeURIComponent(svg)}`
}

// If you don't have official SVGs available, generate colorful circular badge icons on-the-fly
// using inline SVG data URLs. This produces consistent, colorful icons for every skill and
// avoids missing-brand issues. If you later provide official SVG files in `src/assets/skill-icons/`
// we can prefer those instead.
const skillColorMap = {
  Java: '#007396',
  JavaScript: '#f7df1e',
  Python: '#3776AB',
  C: '#00599C',
  'React.js': '#61dafb',
  HTML: '#E34F26',
  'Tailwind CSS': '#38B2AC',
  'Vue.js': '#42b883',
  Vuetify: '#1867C0',
  'Node.js': '#339933',
  Express: '#000000',
  'REST APIs': '#0AB6BC',
  MySQL: '#4479A1',
  MongoDB: '#47A248',
  Firebase: '#FFCA28',
  'Git/GitHub': '#181717',
  Figma: '#F24E1E',
  Canva: '#20A4F3',
  Lucidchart: '#FF6B6B',
  DevOps: '#0AB6BC',
  'Cloud Technologies': '#4285F4',
  Microcontrollers: '#8E44AD',
  IoT: '#FF6A00'
}

// Ensure express is visible on a dark background by preferring the teal brand color
skillColorMap['Express'] = '#0AB6BC'

// Choose icon sizes per-skill (bigger for Tailwind, MongoDB, Firebase)
function getIconSize(skill) {
  // Use a consistent icon size for all skill icons to keep the grid uniform
  // (previously Tailwind/MongoDB/Firebase were larger; normalize to 72px)
  return 72
}

function getIconColor(skill) {
  return skillColorMap[skill] || '#0AB6BC'
}

function svgBadgeDataUrl(label, color) {
  const short = label.split(/[\s\.\/\-]+/).map(s => s[0]).slice(0,2).join('').toUpperCase();
  const svg = `<?xml version="1.0" encoding="UTF-8"?><svg xmlns='http://www.w3.org/2000/svg' width='128' height='128' viewBox='0 0 128 128'>
    <defs>
      <linearGradient id='g' x1='0' x2='1' y1='0' y2='1'>
        <stop offset='0' stop-color='${color}' stop-opacity='1'/>
        <stop offset='1' stop-color='#ffffff' stop-opacity='0.06'/>
      </linearGradient>
    </defs>
    <rect rx='20' width='128' height='128' fill='url(#g)' />
    <text x='50%' y='54%' dominant-baseline='middle' text-anchor='middle' font-family='Inter, Arial, sans-serif' font-size='46' fill='rgba(255,255,255,0.95)'>${short}</text>
  </svg>`
  return `data:image/svg+xml;utf8,${encodeURIComponent(svg)}`
}

function getSkillIconUrl(skill) {
  // 1) prefer simple-icons if we have a mapping
  const si = simpleMap[skill]
  if (si) {
    const url = svgFromSimpleIcon(si)
    if (url) return url
  }
  // 2) prefer local asset under src/assets/skill-icons if present (support svg/png/jpg/jpeg)
  try {
    // use a simple glob (all files) to avoid any brace/glob edge cases
    const localIcons = import.meta.globEager('./assets/skill-icons/*')
    const slug = skill.toString().toLowerCase().replace(/[^a-z0-9]+/g, '-')
    // find any file that starts with the slug (supports png/svg/jpg/etc.)
    for (const k of Object.keys(localIcons)) {
      const base = k.replace('./assets/skill-icons/', '')
      if (base.toLowerCase().startsWith(slug + '.')) {
        const mod = localIcons[k]
        if (mod && mod.default) {
          // Debug: indicate which local icon is being used
          // console.debug(`Using local icon for ${skill}: ${base}`)
          return mod.default
        }
      }
    }
  } catch (e) {
    // ignore – import.meta.globEager may not be available in certain environments
  }

  // 3) final fallback: generated badge SVG (or simple-icon we returned earlier)
  const color = skillColorMap[skill] || '#0AB6BC'
  return svgBadgeDataUrl(skill, color)
}

// return local asset URL if present (same search logic as getSkillIconUrl)
function getLocalIcon(skill) {
  // quick override map for icons we want to ensure are used
  const overrides = {
    'Vuetify': vuetifyIcon,
    'Express': expressIcon
  }
  if (overrides[skill]) return overrides[skill]
  try {
    const localIcons = import.meta.globEager('./assets/skill-icons/*')
    const slug = skill.toString().toLowerCase().replace(/[^a-z0-9]+/g, '-')
    for (const k of Object.keys(localIcons)) {
      const base = k.replace('./assets/skill-icons/', '')
      if (base.toLowerCase().startsWith(slug + '.')) {
        const mod = localIcons[k]
        if (mod && mod.default) return mod.default
      }
    }
  } catch (e) {}
  return null
}

const projects = ref([
  {
    id: 1,
    title: 'Hybrid Workspace Management System',
    description: 'Optimized workspace and parking resource allocation with real-time updates, visual dashboards, and admin panel.',
    technologies: ['React.js', 'Node.js', 'Express', 'MongoDB'],
    github: 'https://github.com/HWMS_frontend',
    hover: false
  },
  {
    id: 2,
    title: 'Cartoon Generator App',
    description: 'Web application integrating OpenAI\'s DALL·E model to generate cartoon-style images from natural language descriptions.',
    technologies: ['React', 'TypeScript', 'Vite', 'OpenAI API'],
    github: 'https://github.com/Sjay2002/dalle-cartoon-generator.git',
    hover: false
  },
  {
    id: 3,
    title: 'Clean World',
    description: 'Community-driven environmental cleanup platform with real-time updates and collaborative opportunities.',
    technologies: ['HTML', 'CSS', 'JavaScript', 'Ballerina', 'MySQL'],
    github: 'https://github.com/mysticoders',
    hover: false
  },
  {
    id: 4,
    title: 'Beatify Music Player',
    description: 'Spotify-inspired music player web application with album browsing and intuitive playback controls.',
    technologies: ['React.js', 'Tailwind CSS'],
    github: 'https://github.com/Sjay2002/Beatify',
    hover: false
  },
  {
    id: 5,
    title: 'E-Commerce Jewelry Shop',
    description: 'Platform designed to sell homemade jewelry with responsive design and user-friendly interface.',
    technologies: ['HTML', 'CSS', 'JavaScript'],
    github: 'https://github.com/WebShop',
    hover: false
  },
  {
    id: 6,
    title: 'Power Measuring Device',
    description: 'IoT solution to measure voltage, current, and power usage with real-time web interface insights.',
    technologies: ['Arduino', 'ESP32', 'Firebase', 'HTML', 'CSS', 'JavaScript'],
    github: '',
    hover: false
  }
])

const skillCategories = ref([
  {
    category: 'Languages',
    skills: ['Java', 'JavaScript', 'Python', 'C']
  },
  {
    category: 'Frontend',
    skills: ['React.js', 'HTML', 'CSS', 'Tailwind CSS', 'Vue.js', 'Vuetify']
  },
  {
    category: 'Backend',
    skills: ['Node.js', 'Express']
  },
  {
    category: 'Databases',
    skills: ['MySQL', 'MongoDB', 'Firebase']
  }
])

const education = ref([
  {
    id: 1,
    degree: 'University of Moratuwa',
    institution: 'BSc (Hons) in Information Technology',
    period: 'Jan 2023 - 2027',
    details: '',
    // logo will be injected below via import
    logo: null
  },
  {
    id: 2,
    degree: 'NIBM Sri Lanka, School of Computing',
    institution: 'Certificate Course in Computer Science',
    period: 'Dec 2022 - May 2023',
    details: '',
    logo: null
  },
  {
    id: 3,
    degree: 'Maliyadeva Girls\' College, Kurunegala',
    institution: 'GCE A/L - Biological Science',
    period: '2013-2022',
    details: '',
    logo: null
  }
  // {
  //   id: 4,
  //   degree: 'GCE O/L',
  //   institution: 'Maliyadeva Girls\' College, Kurunegala',
  //   period: '2018',
  //   details: '9A\'s'
  // }
])

// contact form state
const contactName = ref('')
const contactEmail = ref('')
const contactSubject = ref('')
const contactMessage = ref('')
const sending = ref(false)
const snackbarVisible = ref(false)
const snackbarMessage = ref('')
const snackbarColor = ref('success')

function validateEmail(email) {
  const re = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\\.,;:\s@\"]+\.)+[^<>()[\]\\.,;:\s@\"]{2,})$/i
  return re.test(String(email).toLowerCase())
}

function sendEmail() {
  if (!contactName.value || !contactEmail.value || !contactMessage.value) {
    snackbarMessage.value = 'Please fill name, email and message.'
    snackbarColor.value = 'error'
    snackbarVisible.value = true
    return
  }
  if (!validateEmail(contactEmail.value)) {
    snackbarMessage.value = 'Please provide a valid email address.'
    snackbarColor.value = 'error'
    snackbarVisible.value = true
    return
  }
  // Use Formspree to submit the form serverlessly.
  // 1) Create a form at https://formspree.io and get your form ID (looks like `f/abcd1234`).
  // 2) Replace the FORMSPREE_ENDPOINT below with your full endpoint, e.g.:
  //    const FORMSPREE_ENDPOINT = 'https://formspree.io/f/abcd1234'
  const FORMSPREE_ENDPOINT = 'https://formspree.io/f/xrboayqq'

  if (FORMSPREE_ENDPOINT.includes('<YOUR_FORM_ID>')) {
    snackbarMessage.value = 'Formspree endpoint not configured. Please replace FORMSPREE_ENDPOINT with your form URL.'
    snackbarColor.value = 'error'
    snackbarVisible.value = true
    return
  }

  sending.value = true
  const formData = new FormData()
  formData.append('name', contactName.value)
  formData.append('email', contactEmail.value)
  formData.append('subject', contactSubject.value || 'Message from portfolio site')
  formData.append('message', contactMessage.value)

  // Show immediate feedback while we POST
  snackbarMessage.value = 'Sending message...'
  snackbarColor.value = 'info'
  snackbarVisible.value = true

  fetch(FORMSPREE_ENDPOINT, {
    method: 'POST',
    body: formData,
    headers: {
      'Accept': 'application/json'
    }
  })
  .then(async (res) => {
    sending.value = false
    if (res.ok) {
      snackbarMessage.value = 'Message sent — I will get back to you soon.'
      snackbarColor.value = 'success'
      snackbarVisible.value = true
      contactName.value = ''
      contactEmail.value = ''
      contactSubject.value = ''
      contactMessage.value = ''
    } else {
      // try to parse error details
      let errText = 'Failed to send message.'
      try {
        const j = await res.json()
        if (j && j.error) errText = j.error
      } catch (e) {}
      snackbarMessage.value = errText
      snackbarColor.value = 'error'
      snackbarVisible.value = true
    }
  })
  .catch((err) => {
    sending.value = false
    snackbarMessage.value = 'Network error: could not send message.'
    snackbarColor.value = 'error'
    snackbarVisible.value = true
    console.error('Formspree error', err)
  })
}

// import institute logos placed in src/assets
// Note: filename is `School.png` in the repo (case-sensitive). Use exact filename so production builds on Linux (Vercel) succeed.
import logoSchool from './assets/School.png'
import logoUOM from './assets/uom.png'
import logoNIBM from './assets/NIBM.png'

// attach logos to the education entries (keeps original data structure minimal)
// We mutate the reactive `education` ref here for simplicity
if (education && education.value && Array.isArray(education.value)) {
  for (const e of education.value) {
    if (/moratuwa/i.test(e.degree)) e.logo = logoUOM
    else if (/nibm/i.test(e.degree)) e.logo = logoNIBM
    else if (/maliyadeva/i.test(e.degree)) e.logo = logoSchool
  }
}
</script>

<style scoped>
.portfolio-app {
  /* single global gradient background for the entire site (user requested) */
  background: linear-gradient(135deg, #1d010fff 0%, #0b2030 100%);
  background-attachment: fixed;
  color: #ffffff;
  /* lighter accent used for icon boxes (overrides only icon-related UI) */
  --icon-accent: #66d6d4; /* lighter teal for icon boxes */
  --icon-accent-rgb: 102,214,212;
}

/* ensure the app/container fills the viewport and allows page scrolling over the global background */
html, body, #app, .portfolio-app {
  height: 100%;
}
.portfolio-app {
  min-height: 100vh;
  overflow-y: auto;
}

.navbar {
  z-index: 100;
}

.nav-link {
  color: #d0d0d0;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #0AB6BC;
}

/* Mobile behaviour: hide desktop links and show menu button */
.mobile-menu-button { display: none; }
@media (max-width: 880px) {
  /* On small screens show compact nav links in a single line and hide the hamburger */
  .nav-links {
    display: flex !important;
    gap: 0.35rem !important; /* tighter spacing between tabs on mobile */
    align-items: center;
    justify-content: center;
    font-size: 0.82rem; /* slightly smaller text for tighter fit */
    flex-wrap: nowrap; /* keep items on a single line */
    overflow-x: auto; /* allow scroll if it still overflows slightly */
    padding: 0 0.4rem;
  }
  /* make individual link targets tighter on mobile */
  .nav-links a.nav-link {
    padding: 0.28rem 0.45rem;
    margin: 0;
    font-size: 0.82rem;
    white-space: nowrap;
  }
  /* hide the SJ logo on mobile to maximize space for nav items */
  .logo { display: none !important; }
  /* hide the hamburger button on mobile per request */
  .mobile-menu-button { display: none !important; }
}

/* Drawer link styling */
.mobile-drawer .v-list { padding-top: 1rem; }
.mobile-drawer .drawer-link {
  display: block;
  padding: 0.9rem 1rem;
  color: #cfd8de;
  text-decoration: none;
  font-weight: 600;
}
.mobile-drawer .drawer-link:hover { color: #0AB6BC; }

.hero-section {
  padding-top: 80px;
}

.profile-image {
  /* Disable continuous animation; allow subtle hover zoom only */
  overflow: hidden;
  width: 240px;
  height: 240px;
  margin: 0 auto;
  border-radius: 50%;
}

.profile-image img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  transition: transform 0.35s ease;
  transform: scale(1);
}

.profile-image:hover img {
  transform: scale(1.08); /* small zoom on hover */
}

.project-card {
  cursor: pointer;
  transform: translateY(0);
  transition: all 0.3s ease;
  /* slightly larger cards */
  min-height: 260px;
}

  .project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(var(--icon-accent-rgb), 0.2);
}

/* Slightly larger spacing between technology chips in Featured Projects */
.project-techs {
  gap: 0.75rem; /* a little more space than the utility class */
}

.cta-buttons {
  margin-top: 2rem;
}

/* skill icons and simple animations */
.skill-card {
  overflow: visible;
  /* slightly increase card height for better spacing of icons */
  min-height: 160px;
  padding-top: 1.25rem;
  padding-bottom: 1.25rem;
  /* make skill category container visually transparent (remove dark boxed frame) */
  background: transparent !important;
  border: none !important;
  box-shadow: none !important;
  text-align: center; /* center the category title and content */
}
.skill-chip {
  width: 64px;
  height: 64px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 0; /* remove rounded box */
  background: transparent; /* no box behind icon */
  border: none; /* remove border */
  padding: 4px;
  transition: transform 220ms ease, box-shadow 220ms ease, filter 220ms ease;
  animation: skillFadeUp 380ms ease both;
}
.skill-chip:hover {
  transform: translateY(-6px) scale(1.08);
  filter: drop-shadow(0 0 10px rgba(var(--icon-accent-rgb), 0.35));
}


.skill-icon {
  color: #0AB6BC;
}

.skill-img {
  width: 44px;
  height: 44px;
  display: block;
}

/* New grid-style skill boxes */
.skill-grid {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  align-items: center;
  justify-content: center; /* center boxes horizontally within the card */
  overflow-x: auto; /* keep skills on a single horizontal line and allow scroll on narrow screens */
  padding-bottom: 0.25rem;
}
.skill-box {
  /* slightly lighter card background and border for better contrast */
  background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.02));
  border: 1px solid rgba(255,255,255,0.06);
  border-radius: 12px;
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-width: 140px; /* ensure boxes line up horizontally */
  min-height: 120px;
  transition: transform 220ms ease, box-shadow 220ms ease;
  animation: skillFadeUp 420ms ease both;
  text-align: center; /* ensure label text is centered */
}
.skill-box:hover {
  transform: translateY(-8px);
  box-shadow: 0 18px 36px rgba(var(--icon-accent-rgb), 0.08);
}
.skill-icon-wrap { display:flex; align-items:center; justify-content:center; }
.skill-svg-icon { color: #0AB6BC; }
.skill-img-box { width: 72px; height: 72px; object-fit: contain; }
.skill-label {
  margin-top: 0.75rem;
  font-weight: 700;
  color: #e6eef0; /* slightly lighter label color for better contrast */
  font-size: 0.95rem;
  text-align: center;
}

.skill-card h3 {
  text-align: center; /* center the category heading */
}

@media (max-width: 960px) {
  .skill-grid { gap: 0.75rem; }
}
@media (max-width: 520px) {
  .skill-grid { gap: 0.5rem; }
}

@keyframes skillFadeUp {
  from { opacity: 0; transform: translateY(10px) scale(0.98); }
  to { opacity: 1; transform: translateY(0) scale(1); }
}

/* increase gap between navbar items */
.nav-links {
  column-gap: 2rem; /* larger spacing between nav items */
}

/* timeline vertical connector */
.timeline-wrapper {
  /* switched from a timeline line to a simple list with logos */
  position: relative;
  padding: 0;
}

.timeline-list {
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.timeline-item {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.timeline-logo img {
  width: 64px;
  height: 64px;
  object-fit: contain;
  border-radius: 8px;
  border: 1px solid rgba(255,255,255,0.04);
  background: rgba(255,255,255,0.02);
  padding: 6px;
}

/* Make only the NIBM logo appear on a white background for contrast */
.timeline-logo img.logo-white-bg {
  background: #ffffff !important;
  border: 1px solid rgba(0,0,0,0.06) !important;
}

.timeline-logo-fallback {
  width: 64px;
  height: 64px;
  border-radius: 8px;
  background: rgba(var(--icon-accent-rgb), 0.08);
}

.timeline-content {
  flex: 1 1 auto;
}

/* Hero split layout styles */
.hero-split {
  background: linear-gradient(135deg, #1d010fff 0%, #0b2030 100%);
}
.hero-left {
  padding: 3rem 2rem;
  /* nudge the left column content slightly to the right for better balance */
  padding-left: 8.5rem;
}
.hero-title {
  font-size: 3.2rem;
  line-height: 1.05;
  margin: 0 0 0.5rem 0;
  color: #ffffff;
  font-weight: 700;
  font-family: Georgia, 'Times New Roman', serif;
}
.hero-name { color: #0AB6BC; }
.hero-subtitle {
  color: #32c6d0;
  font-weight: 600;
  margin-bottom: 1rem;
}
.hero-tagline {
  /* distinct, modern sans-serif for the short tagline */
  font-family: 'Poppins', 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-weight: 600;
  font-size: 1.05rem;
  letter-spacing: 0.4px;
  color: #aeeff0;
  margin: 0 0 0.5rem 0;
}

.hero-lead {
  color: #cbd6de;
  max-width: 560px;
}
  .hero-ctas { margin-top: 1.5rem; }
.btn-primary {
  background: linear-gradient(135deg, #0AB6BC, #046b5a) !important;
  color: white !important;
  margin-right: 0.75rem;
}
.btn-outline {
  border: 1px solid rgba(10,182,188,0.28) !important;
  color: #0AB6BC !important;
  background: transparent !important;
}
.hero-ctas {
  /* stack the CTA buttons and place the icon row underneath */
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
  align-items: flex-start;
}

.cta-buttons {
  display: inline-flex;
  gap: 0.9rem;
  align-items: center;
}

/* hero contact icons under CTAs */
.hero-contacts { margin-top: 0.5rem; gap: 0.9rem; }
.hero-contact {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 44px;
  border-radius: 10px;
  transition: transform 160ms ease, box-shadow 160ms ease, background 160ms ease;
  /* lighter box color for better contrast but still subtle */
  background: rgba(255,255,255,0.06);
  border: 1px solid rgba(255,255,255,0.06);
}
.hero-contact:hover { transform: translateY(-4px); box-shadow: 0 12px 24px rgba(var(--icon-accent-rgb), 0.08); }
.hero-contact img.hero-contact-img { width: 26px; height: 26px; object-fit: contain; }

/* Button hover and focus effects */
.hero-ctas .v-btn.btn-primary,
.hero-ctas .v-btn.btn-outline,
.hero-ctas .v-btn.btn-primary.v-btn--is-elevated,
.hero-ctas .v-btn.btn-outline.v-btn--is-elevated {
  transition: transform 180ms ease, box-shadow 180ms ease, opacity 180ms ease;
}
.hero-ctas .v-btn.btn-primary:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 14px 30px rgba(var(--icon-accent-rgb), 0.16);
}
.hero-ctas .v-btn.btn-outline:hover {
  transform: translateY(-4px) scale(1.01);
  box-shadow: 0 10px 22px rgba(var(--icon-accent-rgb), 0.08);
  background: rgba(var(--icon-accent-rgb), 0.04) !important;
}
.hero-ctas .v-btn:focus {
  outline: none;
  box-shadow: 0 0 0 4px rgba(var(--icon-accent-rgb), 0.12);
}
.hero-socials .social-circle {
  display: inline-flex;
  width: 36px;
  height: 36px;
  align-items: center;
  justify-content: center;
  border-radius: 999px;
  background: rgba(255,255,255,0.03);
  color: #0AB6BC;
}
.hero-right { padding: 2rem; }
.hero-image {
  width: 360px;
  max-width: 92%;
  /* outlined framed box with a small gap from the image */
  padding: 10px; /* gap between image and frame */
  border: 2px solid rgba(255,255,255,0.08); /* subtle outline */
  border-radius: 16px;
  background: rgba(255,255,255,0.02);
  overflow: visible;
  position: relative;
  display: inline-block;
  /* soft container shadow to lift the framed box slightly */
  box-shadow: 0 6px 18px rgba(2,8,23,0.4);
}
.hero-image img {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 10px; /* inner image rounded corners to match frame */
  /* entry animation */
  opacity: 0;
  transform-origin: center center;
  animation: imageEnter 820ms cubic-bezier(.2,.9,.2,1) both;
  /* subtle lift shadow beneath the image */
  box-shadow: 0 20px 40px rgba(0,0,0,0.6);
  transform: scale(1.02);
}
.hero-image-overlay {
  display: none; /* removed decorative overlay per request */
}

/* content entrance animation (staggered) */
.hero-title,
.hero-subtitle,
.hero-lead,
.hero-ctas,
.hero-socials {
  opacity: 0;
  transform: translateY(10px);
  animation: contentEnter 680ms cubic-bezier(.2,.9,.2,1) both;
}
.hero-title { animation-delay: 120ms }
.hero-subtitle { animation-delay: 260ms }
.hero-lead { animation-delay: 380ms }
.hero-ctas { animation-delay: 520ms }
.hero-socials { animation-delay: 660ms }

@keyframes contentEnter {
  from { opacity: 0; transform: translateY(10px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes imageEnter {
  from { opacity: 0; transform: translateY(8px) scale(0.98); }
  to   { opacity: 1; transform: translateY(0) scale(1.02); }
}

/* Hover animations for education rows */
.timeline-item {
  transition: transform 260ms cubic-bezier(.2,.9,.2,1), box-shadow 260ms ease;
}
.timeline-item:hover {
  transform: translateY(-6px);
}

.timeline-item .timeline-logo img {
  transition: transform 260ms cubic-bezier(.2,.9,.2,1), box-shadow 260ms ease;
}
.timeline-item:hover .timeline-logo img {
  transform: scale(1.08);
  box-shadow: 0 10px 20px rgba(var(--icon-accent-rgb), 0.12);
}

/* Slight card lift + soft glow on hover */
.timeline-item .v-card {
  transition: transform 260ms cubic-bezier(.2,.9,.2,1), box-shadow 260ms ease, border-color 260ms ease;
}
.timeline-item:hover .v-card {
  transform: translateY(-4px);
  box-shadow: 0 18px 30px rgba(var(--icon-accent-rgb), 0.12);
  border-color: rgba(var(--icon-accent-rgb), 0.24);
}

.contact-info a {
  transition: all 0.3s ease;
}

.contact-info a:hover {
  text-decoration: underline;
}

html {
  scroll-behavior: smooth;
}

/* footer contact icons: increased spacing, subtler boxes (no border), lighter backgrounds */
.footer-contacts {
  gap: 3rem; /* increase spacing so icons are farther apart */
}
.footer-contacts .footer-icon v-icon,
.footer-contacts .footer-icon {
  font-size: 22px;
}
.footer-contacts .footer-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 44px;
  border-radius: 8px;
  transition: transform 180ms ease, background 180ms ease;
  background: #071226; /* lower box opacity */
  border: none; /* remove light color border in footer */
}
.footer-contacts .footer-icon:hover {
  transform: translateY(-4px) scale(1.04);
  background: rgba(var(--icon-accent-rgb), 0.06);
}

/* ensure footer uses the same lighter hero-contact style but without border */
.footer-contacts .hero-contact {
  background: rgba(255,255,255,0.03);
  border: none;
}

/* Ensure Iconify / inline SVGs in the footer are visible on subtle boxes */
.footer-contacts .footer-icon svg,
.footer-contacts .footer-icon svg * {
  fill: #ffffff !important;
  color: #ffffff !important;
}

/* Slightly boost the figma image so it reads on the dark background */
.footer-contacts img.hero-contact-img {
  filter: brightness(1.1) saturate(1.05);
}

/* Light input styles for contact form to improve visibility on light fields */
.light-field input,
.light-field textarea,
.light-field .v-field__control,
.light-field .v-input__control,
.light-field .v-field,
.light-field .v-field__input,
.light-field .v-textarea__control {
  background: #ffffff !important;
  color: #111 !important;
  border-radius: 8px !important;
  padding: 10px 12px !important;
}
.light-field input::placeholder,
.light-field textarea::placeholder {
  color: rgba(0,0,0,0.45) !important;
}
.light-field .v-field__label {
  color: rgba(0,0,0,0.65) !important;
}

/* Ensure Vuetify internal wrappers also show the light background (use :deep(...) for scoped CSS) */
:deep(.light-field .v-field__control),
:deep(.light-field .v-input__control),
:deep(.light-field .v-field__input),
:deep(.light-field .v-textarea__control),
:deep(.light-field input),
:deep(.light-field textarea) {
  background: #ffffff !important;
  color: #111 !important;
  border-radius: 8px !important;
}

/* Remove transparent overlays and bottom borders that make fields appear invisible */
:deep(.light-field .v-field::before),
:deep(.light-field .v-field::after),
:deep(.light-field .v-field__outline),
:deep(.light-field .v-field__border) {
  background: transparent !important;
  border: none !important;
}

/* Make label slightly darker so it's visible on the light field */
:deep(.light-field .v-field__label) {
  color: rgba(0,0,0,0.65) !important;
}

/* About cards layout and styles */
.about-cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
  align-items: stretch; /* ensure equal height for both cards */
}
.about-card {
  /* subtle blue-tinted surface to unify both cards */
  background: linear-gradient(180deg, rgba(var(--icon-accent-rgb), 0.035), rgba(255,255,255,0.006));
  border: 1px solid rgba(var(--icon-accent-rgb), 0.12);
  padding: 1.75rem;
  border-radius: 14px;
  box-shadow: 0 6px 18px rgba(2,8,23,0.4) inset;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: transform 260ms cubic-bezier(.2,.9,.2,1), box-shadow 260ms ease, border-color 260ms ease;
}
/* hover/lift effect for about cards */
.about-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 22px 40px rgba(var(--icon-accent-rgb), 0.14);
  border-color: rgba(var(--icon-accent-rgb), 0.22);
}

/* unified hover for both profile and contact cards */
.profile-card:hover,
.contact-card:hover {
  border-color: rgba(var(--icon-accent-rgb), 0.28);
  box-shadow: 0 20px 38px rgba(var(--icon-accent-rgb), 0.14);
}

.about-card-title {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0 0 0.75rem 0;
  color: #0AB6BC; /* unified blue title color */
}
.about-card-body p {
  color: #cfd8de;
  line-height: 1.75;
  margin-bottom: 1rem;
}
.contact-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.contact-list li {
  display: flex;
  gap: 1rem;
  align-items: center;
}
.contact-icon-link {
  display: inline-flex;
  text-decoration: none; /* remove underline for icon links */
  color: inherit; /* keep icon color controlled by child elements */
}
.contact-icon-link:hover {
  text-decoration: none;
}
.contact-icon {
  color: #ffffff;
  background: #0AB6BC;
  padding: 8px;
  border-radius: 8px;
}
.contact-icon-link:hover .contact-icon { transform: translateY(-3px); box-shadow: 0 8px 18px rgba(var(--icon-accent-rgb), 0.12); }
.contact-label {
  font-weight: 700;
  color: #ffffff;
  font-size: 0.9rem;
}
.contact-link {
  color: #cfd8de;
  text-decoration: none;
}

@media (max-width: 880px) {
  .about-cards { grid-template-columns: 1fr; }
}

@media (max-width: 960px) {
  /* remove the extra left padding on smaller screens so layout stays centered */
  .hero-left { padding-left: 2rem !important; }
}

/* Remove any visible separators between the hero and following sections */
.hero-section,
.projects-section,
.about-section,
.skills-section,
.education-section,
.contact-section {
  border-top: none !important;
  border-bottom: none !important;
  box-shadow: none !important;
  background: transparent !important;
}

/* Slightly extend the about-section animated overlay upwards to cover any 1-2px seam */
.about-section::before {
  top: -2px;
  bottom: -0px;
  height: calc(100% + 2px);
  opacity: 0.45; /* subtle reduction so effect isn't too strong */
}
</style>