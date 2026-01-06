<template>
  <nav :class="{ scrolled: isScrolled }">
    <div class="nav-container">
      <h1 class="logo-name">H<span class="midle-logo">&lt;/&gt;</span>C</h1>

      <button
        class="hamburger"
        :class="{ active: mobileMenuOpen }"
        @click="mobileMenuOpen = !mobileMenuOpen"
        aria-label="Abrir menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <ul :class="{ 'mobile-open': mobileMenuOpen }">
        <li><router-link to="/" @click="closeMenu">Início</router-link></li>
        <li><router-link to="/about" @click="closeMenu">Sobre</router-link></li>
        <li>
          <router-link to="/projects" @click="closeMenu">Projetos</router-link>
        </li>
        <li>
          <router-link to="/contact" @click="closeMenu">Contato</router-link>
        </li>
      </ul>
    </div>
  </nav>

  <section class="home">
    <!-- Hero -->
    <Vue3Lottie
      :animationData="devAnimation"
      class="photo-middle"
      aria-hidden="true"
      alt=""
    />

    <h1 class="titulo-bemvindo">Bem-vindo ao meu portfólio</h1>

    <p class="paragrafo-meio">
      Explore meus projetos e veja como transformo ideias em interfaces claras e
      funcionais.
    </p>

    <!-- Sobre mim -->
    <h2 class="who">Quem sou eu?</h2>

    <p class="paragrafo-quemsoueu">
      Meu nome é <span class="descri">Henry Souza</span>, sou um
      <span class="descri">Desenvolvedor Front-end</span> apaixonado por criar
      interfaces intuitivas e funcionais. Com experiência em tecnologias como
      Vue.js, React e JavaScript, busco transformar ideias em soluções digitais
      eficientes e atraentes.
    </p>

    <router-link to="/about" class="btn-about" @click="closeMenu">
      Mais Informações
    </router-link>

    <h2 class="skills-title">Tecnologias que domino</h2>

    <div class="skills-grid">
      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/vue.js/41B883" alt="Vue.js" />
        <span>Vue.js</span>
      </div>

      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/react/61DAFB" alt="React" />
        <span>React</span>
      </div>

      <div class="skill-item">
        <img
          src="https://cdn.simpleicons.org/javascript/F7DF1E"
          alt="JavaScript"
        />
        <span>JavaScript</span>
      </div>

      <div class="skill-item">
        <img
          src="https://cdn.simpleicons.org/tailwindcss/38BDF8"
          alt="Tailwind CSS"
        />
        <span>Tailwind</span>
      </div>

      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/pinia/FFD43B" alt="Pinia" />
        <span>Pinia</span>
      </div>

      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/firebase/FFCA28" alt="Firebase" />
        <span>Firebase</span>
      </div>

      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/vite/646CFF" alt="Vite" />
        <span>Vite</span>
      </div>

      <div class="skill-item">
        <img src="https://cdn.simpleicons.org/git/F05032" alt="Git" />
        <span>Git</span>
      </div>
    </div>

    <!-- Projetos -->
    <h2 class="projects">Meus Projetos</h2>

    <div class="projects-grid">
      <div class="project-card">
        <div class="project-image">
          <img
            src="@/assets/vida-plus.png"
            alt="Vida Plus - App de saúde e bem-estar"
          />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://vidaplus-bopk.vercel.app/"
                target="_blank"
                rel="noopener"
                class="btn-demo"
              >
                Ver Demo
              </a>
              <a
                href="https://github.com/seuusuario/vida-plus"
                target="_blank"
                rel="noopener"
                class="btn-code"
              >
                <svg
                  width="20"
                  height="20"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                >
                  <path
                    d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                  />
                </svg>
                Código
              </a>
            </div>
          </div>
        </div>

        <div class="project-info">
          <h3 class="project-title">Vida Plus</h3>
          <p class="project-description">
            Aplicativo de saúde e bem-estar com rastreamento de hábitos diários,
            exercícios físicos e planejamento nutricional. Sistema multiusuário
            com perfis de paciente, médico e administrador.
          </p>

          <div class="project-credentials">
            <p class="credentials-title">
              <strong>Credenciais para testar o app:</strong>
            </p>
            <div class="credentials-grid">
              <div class="credential-card">
                <div class="credential-icon">👤</div>
                <div class="credential-info">
                  <strong>Paciente</strong>
                  <p>CPF: <code>000.000.000-00</code></p>
                  <p>Senha: <code>123456</code></p>
                </div>
              </div>
              <div class="credential-card">
                <div class="credential-icon">🩺</div>
                <div class="credential-info">
                  <strong>Médico</strong>
                  <p>CPF: <code>111.111.111-11</code></p>
                  <p>Senha: <code>123456</code></p>
                </div>
              </div>
              <div class="credential-card">
                <div class="credential-icon">⚙️</div>
                <div class="credential-info">
                  <strong>Administrador</strong>
                  <p>CPF: <code>222.222.222-22</code></p>
                  <p>Senha: <code>123456</code></p>
                </div>
              </div>
            </div>
          </div>

          <div class="project-tech">
            <span>Vue.js</span>
            <span>Pinia</span>
            <span>Tailwind</span>
            <span>Firebase</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Call to Action Final -->
    <div class="cta-final">
      <h2>Gostou do meu trabalho?</h2>
      <p>
        Estou aberto para freelas, vagas e novos desafios. Vamos conversar sobre
        seu próximo projeto?
      </p>
      <router-link to="/contact" class="btn-contact"
        >Entre em contato</router-link
      >
    </div>

    <router-link to="/projects" class="btn-view-all">
      Ver todos os projetos →
    </router-link>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Vue3Lottie } from 'vue3-lottie'
import devAnimation from '../assets/lottie/developer.json'

const mobileMenuOpen = ref(false)

const closeMenu = () => {
  mobileMenuOpen.value = false
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=TikTok+Sans:opsz,wght@12..36,300..900&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
}

/* NAVBAR */
nav {
  position: fixed;
  top: 0;
  width: 100%;
  background: #ffffff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  font-family: 'TikTok Sans', sans-serif;
}

.nav-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.75rem 2rem;
  max-width: 1400px;
  margin: 0 auto;
}

.logo-name {
  font-size: 2.5rem;
  font-weight: 800;
  color: #050505;
}

.midle-logo {
  color: #0a07da;
  margin: 0 0.4rem;
}

nav ul {
  display: flex;
  list-style: none;
  gap: 2.5rem;
}

nav ul li a {
  text-decoration: none;
  color: #333;
  font-weight: 600;
  font-size: 1.1rem;
  position: relative;
  transition: color 0.3s ease;
}

nav ul li a:hover {
  color: #0a07da;
}

nav ul li a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -6px;
  left: 0;
  background-color: #0a07da;
  transition: width 0.3s ease;
}

nav ul li a:hover::after {
  width: 100%;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 8px;
}

.hamburger span {
  width: 28px;
  height: 3px;
  background: #333;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(6px, 6px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}

/* HOME */
.home {
  min-height: 100vh;
  padding-top: 10rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #f5f5f5;
  font-family: 'TikTok Sans', sans-serif;
  text-align: center;
}

.photo-middle {
  width: 520px;
  max-width: 90%;
  margin-bottom: 2rem;
}

.titulo-bemvindo {
  font-size: 2.8rem;
  color: #333;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.paragrafo-meio {
  max-width: 680px;
  font-size: 1.3rem;
  color: #666;
  margin-bottom: 5rem;
  line-height: 1.6;
}

.who {
  font-size: 2.4rem;
  color: #333;
  margin: 4rem 0 2rem;
}

.photo-hello {
  width: 320px;
  max-width: 90%;
  margin: 2rem 0;
}

.paragrafo-quemsoueu {
  max-width: 680px;
  font-size: 1.3rem;
  color: #666;
  line-height: 1.7;
  margin-bottom: 3rem;
}

.descri {
  font-weight: 700;
  color: #0a07da;
}

.btn-about {
  display: inline-block;
  padding: 1rem 2.5rem;
  font-size: 1.2rem;
  color: #fff;
  background-color: #0a07da;
  border-radius: 30px;
  text-decoration: none;
  transition: all 0.3s ease;
  margin-bottom: 6rem;
}

.btn-about:hover {
  background-color: #0c0a69;
  transform: translateY(-3px);
  box-shadow: 0 6px 12px rgba(10, 7, 218, 0.2);
}

/* SKILLS - LOGOS OFICIAIS REAIS */
.skills-title {
  font-size: 2.4rem;
  color: #333;
  margin: 2rem 0 1rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 8rem;
  max-width: 1200px;
  width: 100%;
  padding: 0 8rem;
  margin-bottom: 5rem;
}

.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  padding: 1.8rem 0.5rem;
  background: #fff;
  border-radius: 20px;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.4s ease;
}

.skill-item:hover {
  transform: translateY(-12px);
  box-shadow: 0 16px 35px rgba(10, 7, 218, 0.18);
}

.skill-item span {
  font-weight: 700;
  color: #333;
  font-size: 1.1rem;
}

/* PROJETOS */
.projects {
  font-size: 2.4rem;
  color: #333;
  margin-bottom: 3rem;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 2.5rem;
  max-width: 1200px;
  width: 100%;
  padding: 0 1rem;
  margin-bottom: 4rem;
}

.project-card {
  background: #fff;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
  transition: all 0.4s ease;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.project-image {
  position: relative;
  height: 220px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(transparent, rgba(10, 7, 218, 0.9));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.4s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: 1rem;
}

.btn-demo,
.btn-code {
  padding: 0.8rem 1.5rem;
  background: #fff;
  color: #0a07da;
  text-decoration: none;
  border-radius: 30px;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
}

.btn-demo:hover,
.btn-code:hover {
  background: #0a07da;
  color: #fff;
  transform: scale(1.05);
}

.btn-code {
  background: rgba(0, 0, 0, 0.7);
  color: #fff;
}

.btn-code:hover {
  background: #000;
}

.project-info {
  padding: 1.5rem;
}

.project-title {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 0.8rem;
}

.project-description {
  color: #666;
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 1.2rem;
}

/* CREDENCIAIS */
.project-credentials {
  margin: 1.5rem 0;
  padding: 0;
}

.credentials-title {
  text-align: center;
  color: #0a07da;
  font-weight: 600;
  margin-bottom: 1rem;
  font-size: 1.05rem;
}

.credentials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1rem;
}

.credential-card {
  background: #f8f8ff;
  border: 1px solid #e0e0ff;
  border-radius: 12px;
  padding: 1.2rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px rgba(10, 7, 218, 0.05);
}

.credential-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(10, 7, 218, 0.12);
  border-color: #0a07da;
}

.credential-icon {
  font-size: 2.2rem;
  flex-shrink: 0;
}

.credential-info {
  flex: 1;
}

.credential-info strong {
  display: block;
  color: #333;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
}

.credential-info p {
  margin: 0.4rem 0;
  color: #555;
  font-size: 0.95rem;
}

.credential-info code {
  background: #e0e0ff;
  color: #0a07da;
  padding: 0.3rem 0.6rem;
  border-radius: 6px;
  font-family: 'Courier New', monospace;
  font-size: 0.95rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  margin-top: 1rem;
}

.project-tech span {
  background: #e8e7ff;
  color: #0a07da;
  padding: 0.4rem 0.9rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
}

/* CTA FINAL */
.cta-final {
  margin: 6rem 0 4rem;
  padding: 3rem 2rem;
  background: linear-gradient(135deg, #0a07da, #0c0a69);
  border-radius: 20px;
  max-width: 900px;
  width: 100%;
  color: #fff;
  text-align: center;
}

.cta-final h2 {
  font-size: 2.4rem;
  margin-bottom: 1rem;
}

.cta-final p {
  font-size: 1.3rem;
  margin-bottom: 2rem;
  opacity: 0.95;
}

.btn-contact {
  display: inline-block;
  padding: 1.2rem 3rem;
  font-size: 1.3rem;
  background: #fff;
  color: #0a07da;
  font-weight: 700;
  border-radius: 30px;
  text-decoration: none;
  transition: all 0.3s ease;
}

.btn-contact:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  background: #f0f0ff;
}

.btn-view-all {
  display: inline-block;
  margin: 2rem 0 8rem;
  padding: 1rem 2.5rem;
  background: transparent;
  color: #0a07da;
  border: 2px solid #0a07da;
  border-radius: 30px;
  font-size: 1.1rem;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
}

.btn-view-all:hover {
  background: #0a07da;
  color: #fff;
}

/* RESPONSIVIDADE */
@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 2rem;
  }
  .skill-item {
    padding: 1.5rem 0.8rem;
  }
  .skill-item span {
    font-size: 1rem;
  }
  .credentials-grid {
    grid-template-columns: 1fr;
  }
  .cta-final {
    margin: 4rem 1rem;
    padding: 2.5rem 1.5rem;
  }
}

@media (max-width: 768px) {
  .hamburger {
    display: flex;
  }

  nav ul {
    position: fixed;
    top: 70px;
    left: 0;
    width: 100%;
    height: calc(100vh - 70px);
    background: #ffffff;
    flex-direction: column;
    align-items: center;
    padding-top: 4rem;
    gap: 3rem;

    transform: translateX(100%);
    transition: transform 0.4s ease;

    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    z-index: 999;
  }

  nav ul.mobile-open {
    transform: translateX(0);
  }
}
</style>
