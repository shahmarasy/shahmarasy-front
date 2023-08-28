<template>
  <header>
    <div class="wrapper">
      <div class="greetings">
        <h1 class="green">Bahman Messry Shahmarasy</h1>
        <h4 class="comment">// FullStack Developer</h4>
        <div class="desktop">
          <a href="#/">About Me</a>
          | <a href="#/skills">My Skills</a>
          |<a href="#/certificates">My Certificates</a>
          | <a href="#/projects">Recent Projects</a>
          |<a href="#/experience">Work Experience</a>
          | <a href="#/contact">Contact Me</a>
        </div>
        <div class="mobile-center mobile">
          <a href="#/">About Me</a>
          - <a href="#/skills">My Skills</a>
          <br><a href="#/certificates">My Certificates</a>
          - <a href="#/projects">Recent Projects</a>
          <br><a href="#/experience">Work Experience</a>
          - <a href="#/contact">Contact Me</a>
        </div>
      </div>

      <hr class="header_hr">
    </div>
  </header>

  <component :is="currentView" />

  <div class="created">
    <div class="clogo">
      <div class="footerText">This Site Is Powered By:</div>
      <img class="flask" src="@/assets/Flask_logo.svg" alt="Flask Framework">
      <img class="vuejs" src="@/assets/Vue_logo.svg" alt="VueJS">
      <img class="redis" src="@/assets/Redis_logo.svg" alt="Redis">
      <img class="github" src="@/assets/Github_logo.svg" alt="Github">
    </div>

  </div>
</template>
<script>
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Experience from './components/Experience.vue'
import Certificates from './components/Certificates.vue'
import Contact from './components/Contact.vue'
import NotFound from './components/NotFound.vue'


const routes = {
  '/': About,
  '/skills': Skills,
  '/projects': Projects,
  '/experience': Experience,
  '/certificates': Certificates,
  '/contact': Contact,
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash
    })
  }
}
</script>
