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
          Sithumini Jayasekara
        </div>
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

    <!-- Hero Section -->
    <section id="home" class="hero-section" style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%)">
      <v-container class="d-flex align-center justify-center" style="min-height: 100vh">
        <div class="text-center">
          <div class="profile-image mb-6">
            <v-avatar size="240" style="background: linear-gradient(135deg, #0AB6BC, #045C43); overflow: hidden;">
              <img :src="profileImg" alt="Sithumini"/>
            </v-avatar>
          </div>
          <h1 class="text-h2 font-weight-bold mb-4" style="color: #ffffff">
            Sithumini Jayasekara
          </h1>
          <p class="text-h5 mb-6" style="color: #0AB6BC">
            Software Engineer | Full-Stack Developer | Tech Enthusiast
          </p>
          <p class="text-body1 mb-8" style="color: #b0b0b0; max-width: 600px; margin: 0 auto">
            Third-year undergraduate pursuing BSc (Hons) in Information Technology at the University of Moratuwa. 
            Skilled in full-stack development, DevOps, and cloud technologies with hands-on experience building scalable applications.
          </p>
          <div class="cta-buttons d-flex gap-4 justify-center">
            <v-btn
              size="large"
              style="background: linear-gradient(135deg, #0AB6BC, #045C43); color: white"
              href="#projects"
            >
              View My Work
            </v-btn>
            <v-btn
              size="large"
              variant="outlined"
              style="border-color: #0AB6BC; color: #0AB6BC"
              href="#contact"
            >
              Get In Touch
            </v-btn>
          </div>
        </div>
      </v-container>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section py-16" style="background: #0f1419">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-8 text-center" style="color: #0AB6BC">
          About Me
        </h2>
        <v-row>
          <v-col cols="12" md="6">
            <p class="text-body1 mb-4" style="color: #d0d0d0; line-height: 1.8">
              I'm a passionate software engineer with a strong foundation in full-stack development. 
              Currently pursuing my degree at the University of Moratuwa, I've gained practical experience 
              through internships and personal projects.
            </p>
            <p class="text-body1 mb-4" style="color: #d0d0d0; line-height: 1.8">
              My expertise spans across frontend technologies like React.js and backend development with Node.js and Express. 
              I'm particularly interested in building scalable applications and optimizing system performance.
            </p>
            <p class="text-body1" style="color: #d0d0d0; line-height: 1.8">
              Beyond coding, I'm an active volunteer in my community, serving as an organizing committee member 
              for various tech events and competitions.
            </p>
          </v-col>
          <v-col cols="12" md="6">
            <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
              <v-card-text>
                <div class="mb-6">
                  <h3 style="color: #0AB6BC" class="font-weight-bold mb-2">Quick Facts</h3>
                  <ul style="color: #d0d0d0; list-style: none; padding: 0">
                    <li class="mb-3">📍 Location: Sri Lanka</li>
                    <li class="mb-3">🎓 University: University of Moratuwa</li>
                    <li class="mb-3">📊 CGPA: 3.45</li>
                    <li class="mb-3">💼 Role: Software Engineer Intern</li>
                    <li class="mb-3">🎯 Focus: Full-Stack Development & DevOps</li>
                  </ul>
                </div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects-section py-16" style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%)">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Featured Projects
        </h2>
        <v-row>
          <v-col v-for="project in projects" :key="project.id" cols="12" md="6" lg="4">
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
                  <div class="d-flex flex-wrap gap-2">
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
    <section id="skills" class="skills-section py-16" style="background: #0f1419">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Skills & Expertise
        </h2>
        <v-row>
          <v-col v-for="skillCategory in skillCategories" :key="skillCategory.category" cols="12" md="6">
            <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
              <v-card-text>
                <h3 style="color: #0AB6BC" class="font-weight-bold mb-4">{{ skillCategory.category }}</h3>
                <div class="d-flex flex-wrap gap-2">
                  <v-chip
                    v-for="skill in skillCategory.skills"
                    :key="skill"
                    style="background: linear-gradient(135deg, #0AB6BC, #045C43); color: white"
                  >
                    {{ skill }}
                  </v-chip>
                </div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <!-- Education Section -->
    <section id="education" class="education-section py-16" style="background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%)">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Education
        </h2>
        <div class="timeline-wrapper">
          <v-timeline side="end">
            <v-timeline-item
              v-for="edu in education"
              :key="edu.id"
              dot-color="#0AB6BC"
              size="large"
            >
              <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
                <v-card-text>
                  <h3 style="color: #0AB6BC" class="font-weight-bold">{{ edu.degree }}</h3>
                  <p style="color: #d0d0d0" class="text-body2 mb-2">{{ edu.institution }}</p>
                  <p style="color: #0AB6BC" class="text-caption font-weight-bold">{{ edu.period }}</p>
                  <p v-if="edu.details" style="color: #b0b0b0" class="text-body2 mt-2">{{ edu.details }}</p>
                </v-card-text>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </div>
      </v-container>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact-section py-16" style="background: #0f1419">
      <v-container>
        <h2 class="text-h3 font-weight-bold mb-12 text-center" style="color: #0AB6BC">
          Get In Touch
        </h2>
        <v-row justify="center">
          <v-col cols="12" md="8">
            <v-card style="background: linear-gradient(135deg, #1a1f3a 0%, #0f1419 100%); border: 1px solid #0AB6BC">
              <v-card-text>
                <div class="text-center mb-8">
                  <p style="color: #d0d0d0" class="text-body1 mb-6">
                    I'm always interested in hearing about new projects and opportunities. 
                    Feel free to reach out!
                  </p>
                </div>
                <div class="contact-info d-flex flex-column gap-4">
                  <div class="d-flex align-center gap-4">
                    <v-icon style="color: #0AB6BC">mdi-email</v-icon>
                    <a href="mailto:sithuminijayasekara6@gmail.com" style="color: #0AB6BC; text-decoration: none">
                      sithuminijayasekara6@gmail.com
                    </a>
                  </div>
                  <div class="d-flex align-center gap-4">
                    <v-icon style="color: #0AB6BC">mdi-phone</v-icon>
                    <a href="tel:+94713448461" style="color: #0AB6BC; text-decoration: none">
                      +94 (71) 344 8461
                    </a>
                  </div>
                  <div class="d-flex align-center gap-4">
                    <v-icon style="color: #0AB6BC">mdi-linkedin</v-icon>
                    <a href="https://www.linkedin.com" target="_blank" style="color: #0AB6BC; text-decoration: none">
                      LinkedIn Profile
                    </a>
                  </div>
                  <div class="d-flex align-center gap-4">
                    <v-icon style="color: #0AB6BC">mdi-github</v-icon>
                    <a href="https://github.com/Sjay2002" target="_blank" style="color: #0AB6BC; text-decoration: none">
                      GitHub Profile
                    </a>
                  </div>
                  <div class="d-flex align-center gap-4">
                    <v-icon style="color: #0AB6BC">mdi-figma</v-icon>
                    <a href="https://www.figma.com/@sjay2" target="_blank" style="color: #0AB6BC; text-decoration: none">
                      Figma Portfolio
                    </a>
                  </div>
                </div>
                <div class="mt-8 text-center">
                  <v-btn
                    size="large"
                    style="background: linear-gradient(135deg, #0AB6BC, #045C43); color: white"
                    href="mailto:sithuminijayasekara6@gmail.com"
                  >
                    Send Me an Email
                  </v-btn>
                </div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

    <!-- Footer -->
    <footer style="background: #0a0e27; border-top: 1px solid #0AB6BC; padding: 2rem 0">
      <v-container>
        <div class="text-center">
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
import profileImg from './assets/my.jpg'

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
    skills: ['React.js', 'HTML', 'Tailwind CSS', 'Vue.js', 'Vuetify']
  },
  {
    category: 'Backend',
    skills: ['Node.js', 'Express', 'REST APIs']
  },
  {
    category: 'Databases',
    skills: ['MySQL', 'MongoDB', 'Firebase']
  },
  {
    category: 'Tools & Platforms',
    skills: ['Git/GitHub', 'Figma', 'Canva', 'Lucidchart']
  },
  {
    category: 'Other',
    skills: ['DevOps', 'Cloud Technologies', 'Microcontrollers', 'IoT']
  }
])

const education = ref([
  {
    id: 1,
    degree: 'BSc (Hons) in Information Technology',
    institution: 'University of Moratuwa',
    period: 'Jan 2023 - 2027',
    details: 'CGPA: 3.45'
  },
  {
    id: 2,
    degree: 'Certificate Course in Computer Science',
    institution: 'NIBM Sri Lanka, School of Computing',
    period: 'Dec 2022 - May 2023',
    details: ''
  },
  {
    id: 3,
    degree: 'GCE A/L - Biological Science',
    institution: 'Maliyadeva Girls\' College, Kurunegala',
    period: '2021',
    details: 'Z-score: 1.8036 | Physics (A), Chemistry (A), Biology (B)'
  },
  {
    id: 4,
    degree: 'GCE O/L',
    institution: 'Maliyadeva Girls\' College, Kurunegala',
    period: '2018',
    details: '9A\'s'
  }
])
</script>

<style scoped>
.portfolio-app {
  /* yellowish galaxy background with subtle radial highlights */
  background-color: #0a0e27;
  background-image: radial-gradient(circle at 15% 10%, rgba(255,223,128,0.06) 0%, rgba(255,223,128,0.02) 8%, transparent 18%),
                    radial-gradient(circle at 85% 80%, rgba(255,240,180,0.03) 0%, transparent 20%),
                    linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
  background-attachment: fixed;
  color: #ffffff;
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
}

.project-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 24px rgba(10, 182, 188, 0.2);
}

.cta-buttons {
  margin-top: 2rem;
}

/* increase gap between navbar items */
.nav-links {
  column-gap: 2rem; /* larger spacing between nav items */
}

/* timeline vertical connector */
.timeline-wrapper {
  position: relative;
  padding-left: 56px; /* leave space for the line and dots */
}
.timeline-wrapper::before {
  content: "";
  position: absolute;
  left: 28px;
  top: 12px;
  bottom: 12px;
  width: 2px;
  background: linear-gradient(180deg, rgba(10,182,188,0.9), rgba(255,223,128,0.18));
  border-radius: 2px;
  z-index: 0;
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
</style>