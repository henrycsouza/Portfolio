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

  <section class="projects-page">
    <!-- Formas decorativas sutis -->
    <div class="bg-shape shape-circle-1"></div>
    <div class="bg-shape shape-circle-2"></div>
    <div class="bg-shape shape-line-1"></div>

    <!-- Header -->
    <div class="projects-header">
      <h1>Meus Projetos</h1>
      <p>
        Aqui estão alguns dos trabalhos que mais me orgulho. Cada um representa
        aprendizado, criatividade e dedicação.
      </p>
    </div>

    <!-- Grid de Projetos de Código -->
    <div class="projects-grid">
      <!-- Vida Plus -->
      <div class="project-card">
        <div class="project-image">
          <img
            src="@/assets/vida-plus.png"
            alt="Vida Plus - App de saúde"
            loading="lazy"
          />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://vidaplus-bopk.vercel.app/"
                target="_blank"
                rel="noopener"
                class="btn-demo"
                >Ver Demo</a
              >
              <a
                href="https://github.com/henrycsouza/vidaplus"
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
          <h3>Vida Plus</h3>
          <p>
            Aplicativo completo de saúde e bem-estar com rastreamento de
            hábitos, exercícios e nutrição. Sistema multiusuário.
          </p>
          <div class="project-tech">
            <span>Vue.js</span>
            <span>Pinia</span>
            <span>Tailwind</span>
            <span>Firebase</span>
          </div>
        </div>
      </div>

      <!-- Youtube Music Clone -->
      <div class="project-card">
        <div class="project-image">
          <img
            src="@/assets/youtube.png"
            alt="Youtube Music Clone"
            loading="lazy"
          />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://youtube-port.vercel.app/"
                target="_blank"
                rel="noopener"
                class="btn-demo"
                >Ver Demo</a
              >
            </div>
          </div>
        </div>
        <div class="project-info">
          <h3>Youtube Music Clone</h3>
          <p>
            Clone da interface do Youtube Music com navegação e layout
            responsivo.
          </p>
          <div class="project-tech">
            <span>HTML</span>
            <span>CSS</span>
            <span>JavaScript</span>
          </div>
        </div>
      </div>

      <!-- Fortnite Site -->
      <div class="project-card">
        <div class="project-image">
          <img
            src="@/assets/fortnite.png"
            alt="Site do Fortnite"
            loading="lazy"
          />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://fortnite-web.vercel.app/index.html"
                target="_blank"
                rel="noopener"
                class="btn-demo"
                >Ver Demo</a
              >
            </div>
          </div>
        </div>
        <div class="project-info">
          <h3>Site do Fortnite</h3>
          <p>
            Site promocional do jogo Fortnite com foco em design moderno e
            explicação do game.
          </p>
          <div class="project-tech">
            <span>HTML</span>
            <span>CSS</span>
            <span>JavaScript</span>
          </div>
        </div>
      </div>

      <!-- Jogo do Número Secreto -->
      <div class="project-card">
        <div class="project-image">
          <img
            src="@/assets/game.png"
            alt="Jogo do Número Secreto"
            loading="lazy"
          />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://secret-number-pied.vercel.app/"
                target="_blank"
                rel="noopener"
                class="btn-demo"
                >Ver Demo</a
              >
            </div>
          </div>
        </div>
        <div class="project-info">
          <h3>Jogo do Número Secreto</h3>
          <p>
            Jogo interativo onde o usuário adivinha um número aleatório com
            feedback em voz.
          </p>
          <div class="project-tech">
            <span>HTML</span>
            <span>CSS</span>
            <span>JavaScript</span>
          </div>
        </div>
      </div>

      <!-- Alura Books -->
      <div class="project-card">
        <div class="project-image">
          <img src="@/assets/alurabooks.png" alt="Alura Books" loading="lazy" />
          <div class="project-overlay">
            <div class="project-links">
              <a
                href="https://alura-book-bvcpip69n-henrys-projects-180969ba.vercel.app/"
                target="_blank"
                rel="noopener"
                class="btn-demo"
                >Ver Demo</a
              >
            </div>
          </div>
        </div>
        <div class="project-info">
          <h3>Alura Books</h3>
          <p>
            Site de catálogo de livros com layout responsivo e navegação fluida.
          </p>
          <div class="project-tech">
            <span>HTML</span>
            <span>CSS</span>
            <span>JavaScript</span>
          </div>
        </div>
      </div>
    </div>

    <!-- Seção de Designs com Carrosséis por Grupo -->
    <div class="designs-section">
      <h2 class="designs-title">Designs & Protótipos</h2>
      <p class="designs-subtitle">Trabalhos de UI/UX e modelagem no Figma</p>

      <!-- Grupo 1: Futebol -->
      <div class="design-group">
        <h3 class="group-title">Tema Futebol</h3>
        <div class="carousel-container">
          <button class="carousel-btn prev" @click="scrollLeft('futebol')">
            ←
          </button>
          <div class="carousel-track" id="futebol">
            <div class="design-card">
              <img
                src="@/assets/primeiro.jpeg"
                alt="Futebol 1"
                loading="lazy"
              />
              <div class="design-overlay"><p>Projeto de estudo</p></div>
            </div>
            <div class="design-card">
              <img src="@/assets/segundo.jpeg" alt="Futebol 2" loading="lazy" />
              <div class="design-overlay"><p>Projeto para Rede Social</p></div>
            </div>
            <div class="design-card">
              <img
                src="@/assets/terceiro.jpeg"
                alt="Futebol 3"
                loading="lazy"
              />
              <div class="design-overlay"><p>Projeto Raphinha</p></div>
            </div>
            <div class="design-card">
              <img src="@/assets/quarto.jpeg" alt="Futebol 4" loading="lazy" />
              <div class="design-overlay">
                <p>Projeto Corinthians x Cruzeiro</p>
              </div>
            </div>
            <div class="design-card">
              <img src="@/assets/quinto.jpeg" alt="Futebol 5" loading="lazy" />
              <div class="design-overlay">
                <p>Projeto Corinthians x Botafogo</p>
              </div>
            </div>
            <div class="design-card">
              <img src="@/assets/sexto.jpeg" alt="Futebol 6" loading="lazy" />
              <div class="design-overlay"><p>Projeto Raphinha</p></div>
            </div>
          </div>
          <button class="carousel-btn next" @click="scrollRight('futebol')">
            →
          </button>
        </div>
      </div>

      <!-- Grupo 2: ChiaraClean -->
      <div class="design-group">
        <h3 class="group-title">ChiaraClean - Serviço de Limpeza pós-obra</h3>
        <div class="carousel-container">
          <button class="carousel-btn prev" @click="scrollLeft('chiara')">
            ←
          </button>
          <div class="carousel-track" id="chiara">
            <div class="design-card">
              <img
                src="@/assets/setimo.jpeg"
                alt="ChiaraClean 1"
                loading="lazy"
              />
              <div class="design-overlay"><p>Projeto 1</p></div>
            </div>
            <div class="design-card">
              <img
                src="@/assets/decimo_primeiro.jpeg"
                alt="ChiaraClean 2"
                loading="lazy"
              />
              <div class="design-overlay"><p>Projeto 2</p></div>
            </div>
          </div>
          <button class="carousel-btn next" @click="scrollRight('chiara')">
            →
          </button>
        </div>
      </div>

      <!-- Grupo 3: Boteco do Marujo -->
      <div class="design-group">
        <h3 class="group-title">Boteco do Marujo - Rede Social</h3>
        <div class="carousel-container">
          <button class="carousel-btn prev" @click="scrollLeft('boteco')">
            ←
          </button>
          <div class="carousel-track" id="boteco">
            <div class="design-card">
              <img src="@/assets/oitavo.jpeg" alt="Boteco 1" loading="lazy" />
              <div class="design-overlay"><p>Projeto 1</p></div>
            </div>
            <div class="design-card">
              <img src="@/assets/nono.jpeg" alt="Boteco 2" loading="lazy" />
              <div class="design-overlay"><p>Projeto 2</p></div>
            </div>
            <div class="design-card">
              <img src="@/assets/decimo.jpeg" alt="Boteco 3" loading="lazy" />
              <div class="design-overlay"><p>Projeto 3</p></div>
            </div>
            <div class="design-card">
              <img
                src="@/assets/decimo_segundo.jpeg"
                alt="Boteco 4"
                loading="lazy"
              />
              <div class="design-overlay"><p>Projeto 4</p></div>
            </div>
          </div>
          <button class="carousel-btn next" @click="scrollRight('boteco')">
            →
          </button>
        </div>
      </div>

      <!-- Grupo 4: Modelagem 3D -->
      <div class="design-group">
        <h3 class="group-title">Modelagem 3D</h3>
        <div class="carousel-container">
          <button class="carousel-btn prev" @click="scrollLeft('modelagem')">
            ←
          </button>
          <div class="carousel-track" id="modelagem">
            <div class="design-card">
              <img
                src="@/assets/decimo_terceiro.jpeg"
                alt="Ninja 3D"
                loading="lazy"
              />
              <div class="design-overlay"><p>Modelagem Ninja</p></div>
            </div>
            <div class="design-card">
              <img
                src="@/assets/decimo_quarto.jpeg"
                alt="Fortnite 3D"
                loading="lazy"
              />
              <div class="design-overlay"><p>Modelagem Fortnite</p></div>
            </div>
          </div>
          <button class="carousel-btn next" @click="scrollRight('modelagem')">
            →
          </button>
        </div>
      </div>
    </div>

    <!-- CTA Final -->
    <div class="projects-cta">
      <h2>Quer ver mais ou conversar sobre um projeto?</h2>
      <router-link to="/contact" class="btn-contact-projects">
        Fale comigo
      </router-link>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const mobileMenuOpen = ref(false)
const isScrolled = ref(false)

const closeMenu = () => {
  mobileMenuOpen.value = false
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

// Funções do carrossel
const scrollLeft = (id) => {
  const track = document.getElementById(id)
  if (track) track.scrollBy({ left: -340, behavior: 'smooth' })
}

const scrollRight = (id) => {
  const track = document.getElementById(id)
  if (track) track.scrollBy({ left: 340, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  // Animação inicial garantida
  const elements = document.querySelectorAll(
    '.project-card, .design-card, .projects-header, .designs-title, .group-title'
  )
  elements.forEach((el, index) => {
    setTimeout(() => {
      el.style.opacity = 1
      el.style.transform = 'translateY(0)'
    }, index * 80)
  })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
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

/* NAVBAR FIXA */
nav {
  position: fixed;
  top: 0;
  width: 100%;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(12px);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  transition: all 0.4s ease;
  font-family: 'TikTok Sans', sans-serif;
}

nav.scrolled {
  background: #ffffff;
  box-shadow: 0 6px 30px rgba(0, 0, 0, 0.15);
}

.nav-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.8rem 2rem;
  max-width: 1400px;
  margin: 0 auto;
}

.logo-name {
  font-size: 2.6rem;
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
  gap: 2.8rem;
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
  height: 3px;
  bottom: -8px;
  left: 0;
  background-color: #0a07da;
  transition: width 0.4s ease;
}

nav ul li a:hover::after {
  width: 100%;
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 6px;
  background: none;
  border: none;
  cursor: pointer;
}

.hamburger span {
  width: 30px;
  height: 3px;
  background: #333;
  border-radius: 3px;
  transition: all 0.4s ease;
}

.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(8px, -8px);
}

/* PROJECTS PAGE */
.projects-page {
  min-height: 100vh;
  padding-top: 10rem;
  background: linear-gradient(135deg, #f9fcff 0%, #f0f5ff 100%);
  position: relative;
  overflow: hidden;
  font-family: 'TikTok Sans', sans-serif;
}

/* Formas decorativas */
.bg-shape {
  position: absolute;
  opacity: 0.1;
  pointer-events: none;
  z-index: 0;
  animation: float 30s infinite ease-in-out;
}

.shape-circle-1 {
  width: 800px;
  height: 800px;
  background: radial-gradient(circle, #0a07da 0%, transparent 70%);
  top: 10%;
  right: -300px;
  border-radius: 50%;
}

.shape-circle-2 {
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, #0c0a69 0%, transparent 65%);
  bottom: 20%;
  left: -200px;
  border-radius: 50%;
}

.shape-line-1 {
  width: 1000px;
  height: 4px;
  background: linear-gradient(to right, transparent, #0a07da, transparent);
  top: 50%;
  left: -300px;
  transform: rotate(15deg);
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0) translateX(0);
  }
  50% {
    transform: translateY(-80px) translateX(60px);
  }
}

/* Header */
.projects-header {
  text-align: center;
  padding: 4rem 2rem 6rem;
  max-width: 900px;
  margin: 0 auto;
  z-index: 1;
  position: relative;
}

.projects-header h1 {
  font-size: 3.5rem;
  color: #333;
  margin-bottom: 1.5rem;
}

.projects-header p {
  font-size: 1.4rem;
  color: #666;
  line-height: 1.8;
}

/* Grid de Projetos de Código */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
  gap: 3.5rem;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem 6rem;
  position: relative;
  z-index: 1;
}

.project-card {
  background: #fff;
  border-radius: 28px;
  overflow: hidden;
  box-shadow: 0 12px 35px rgba(0, 0, 0, 0.1);
  transition: all 0.6s ease;
  opacity: 0;
  transform: translateY(60px);
}

.project-card:hover {
  transform: translateY(-20px);
  box-shadow: 0 30px 70px rgba(10, 7, 218, 0.2);
}

.project-image {
  position: relative;
  height: 260px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.7s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.15);
}

.project-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(transparent, rgba(10, 7, 218, 0.95));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: 1.5rem;
}

.btn-demo,
.btn-code {
  padding: 1rem 2rem;
  background: #fff;
  color: #0a07da;
  text-decoration: none;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1.1rem;
  display: flex;
  align-items: center;
  gap: 0.8rem;
  transition: all 0.4s ease;
}

.btn-demo:hover,
.btn-code:hover {
  background: #0a07da;
  color: #fff;
  transform: scale(1.1);
}

.btn-code {
  background: rgba(0, 0, 0, 0.8);
  color: #fff;
}

.project-info {
  padding: 2.2rem;
}

.project-info h3 {
  font-size: 1.9rem;
  color: #333;
  margin-bottom: 1rem;
}

.project-info p {
  font-size: 1.15rem;
  color: #666;
  line-height: 1.8;
  margin-bottom: 1.8rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.project-tech span {
  background: #e8e7ff;
  color: #0a07da;
  padding: 0.7rem 1.4rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
}

/* SEÇÃO DE DESIGNS COM CARROSSEL */
.designs-section {
  padding: 8rem 2rem;
  text-align: center;
  background: rgba(255, 255, 255, 0.7);
  position: relative;
  z-index: 1;
}

.designs-title {
  font-size: 3.2rem;
  color: #333;
  margin-bottom: 1rem;
}

.designs-subtitle {
  font-size: 1.5rem;
  color: #666;
  margin-bottom: 5rem;
}

.design-group {
  margin-bottom: 6rem;
}

.group-title {
  font-size: 2.6rem;
  color: #0a07da;
  margin-bottom: 3rem;
  position: relative;
}

.group-title::after {
  content: '';
  position: absolute;
  width: 100px;
  height: 4px;
  background: #0a07da;
  bottom: -12px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 2px;
}

.carousel-container {
  position: relative;
  max-width: 1400px;
  margin: 0 auto;
}

.carousel-track {
  display: flex;
  gap: 2.5rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 1rem 0;
  scrollbar-width: none;
}

.carousel-track::-webkit-scrollbar {
  display: none;
}

.design-card {
  min-width: 340px;
  position: relative;
  border-radius: 28px;
  overflow: hidden;
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.12);
  transition: all 0.6s ease;
  opacity: 0;
  transform: translateY(60px);
}

.design-card:hover {
  transform: translateY(-20px);
  box-shadow: 0 30px 70px rgba(10, 7, 218, 0.2);
}

.design-card img {
  width: 100%;
  height: 420px;
  object-fit: cover;
}

.design-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 2.5rem;
  background: linear-gradient(transparent, rgba(10, 7, 218, 0.9));
  color: #fff;
  font-size: 1.4rem;
  font-weight: 600;
  text-align: center;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.design-card:hover .design-overlay {
  opacity: 1;
}

.carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(10, 7, 218, 0.8);
  color: #fff;
  border: none;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 1.8rem;
  cursor: pointer;
  z-index: 10;
  transition: all 0.3s ease;
}

.carousel-btn:hover {
  background: #0a07da;
  transform: translateY(-50%) scale(1.1);
}

.prev {
  left: 10px;
}

.next {
  right: 10px;
}

/* CTA Final */
.projects-cta {
  text-align: center;
  padding: 8rem 2rem;
  position: relative;
  z-index: 1;
}

.projects-cta h2 {
  font-size: 3rem;
  color: #333;
  margin-bottom: 1.5rem;
}

.btn-contact-projects {
  display: inline-block;
  padding: 1.6rem 4.5rem;
  font-size: 1.5rem;
  background: linear-gradient(135deg, #0a07da, #0c0a69);
  color: #fff;
  font-weight: 700;
  border-radius: 60px;
  text-decoration: none;
  box-shadow: 0 20px 50px rgba(10, 7, 218, 0.3);
  transition: all 0.5s ease;
}

.btn-contact-projects:hover {
  transform: translateY(-12px);
  box-shadow: 0 30px 70px rgba(10, 7, 218, 0.4);
}

/* RESPONSIVIDADE */
@media (max-width: 768px) {
  .carousel-btn {
    display: none;
  }

  .carousel-track {
    padding: 0 1rem;
  }

  .design-card {
    min-width: 300px;
  }

  .design-card img {
    height: 360px;
  }

  .group-title {
    font-size: 2.2rem;
  }
}

@media (max-width: 480px) {
  .projects-header h1 {
    font-size: 2.8rem;
  }

  .group-title {
    font-size: 2rem;
  }

  .design-card img {
    height: 300px;
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
