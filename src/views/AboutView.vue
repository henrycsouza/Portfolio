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

  <section class="about">
    <!-- Formas decorativas flutuantes no fundo -->
    <div class="bg-shape shape-circle-1"></div>
    <div class="bg-shape shape-circle-2"></div>
    <div class="bg-shape shape-circle-3"></div>
    <div class="bg-shape shape-line-1"></div>
    <div class="bg-shape shape-line-2"></div>

    <!-- Hero com animação -->
    <div class="about-hero fade-in">
      <Vue3Lottie
        :animationData="meAnimation"
        :loop="false"
        :autoplay="true"
        class="lottie-hero"
        aria-hidden="true"
      />
      <h1 class="hero-title">Henry Souza</h1>
      <p class="hero-subtitle">Desenvolvedor Front-end</p>
    </div>

    <!-- Seções alternadas -->
    <div class="about-sections">
      <!-- Bloco 1 - Esquerda -->
      <div class="about-block left fade-in-left">
        <div class="block-content">
          <h2>Quem sou eu?</h2>
          <p>
            Olá! Sou um desenvolvedor front-end apaixonado por criar interfaces
            bonitas, intuitivas e funcionais.
          </p>
          <p>
            Transformo ideias em experiências digitais que as pessoas amam usar.
          </p>
        </div>
      </div>

      <div class="section-divider"></div>

      <!-- Bloco 2 - Direita -->
      <div class="about-block right fade-in-right">
        <div class="block-content">
          <h2>Tecnologias que domino</h2>
          <p>Trabalho com as ferramentas mais modernas do mercado:</p>
          <div class="tech-tags">
            <span>Vue.js</span>
            <span>React</span>
            <span>JavaScript</span>
            <span>Tailwind CSS</span>
            <span>Pinia</span>
            <span>Firebase</span>
            <span>Vite</span>
            <span>Git</span>
          </div>
        </div>
      </div>

      <div class="section-divider"></div>

      <!-- Bloco 3 - Esquerda -->
      <div class="about-block left fade-in-left">
        <div class="block-content">
          <h2>O que me move</h2>
          <p>
            Acredito que um bom código + design incrível faz toda a diferença.
          </p>
          <p>
            Meu foco é entregar soluções rápidas, acessíveis e com atenção aos
            detalhes.
          </p>
        </div>
      </div>

      <div class="section-divider"></div>

      <!-- Bloco 4 - Direita -->
      <div class="about-block right fade-in-right">
        <div class="block-content">
          <h2>Formação e interesses</h2>
          <p>
            <strong>Formação:</strong> Análise e Desenvolvimento de Sistemas
          </p>
          <p>
            <strong>Interesses:</strong> UI/UX Design, animações web,
            performance, acessibilidade e código limpo
          </p>
        </div>
      </div>

      <div class="section-divider"></div>

      <!-- CTA Final -->
      <div class="about-cta-block fade-in">
        <h2>Vamos trabalhar juntos?</h2>
        <p>Estou aberto para freelas, vagas e novos desafios.</p>
        <router-link to="/contact" class="btn-contact-large">
          Entre em contato
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Vue3Lottie } from 'vue3-lottie'
import meAnimation from '@/assets/lottie/meAnimation.json'

const mobileMenuOpen = ref(false)
const isScrolled = ref(false)

const closeMenu = () => {
  mobileMenuOpen.value = false
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible')
        } else {
          entry.target.classList.remove('visible')
        }
      })
    },
    { threshold: 0.15, rootMargin: '0px 0px -50px 0px' }
  )

  document
    .querySelectorAll('.fade-in, .fade-in-left, .fade-in-right')
    .forEach((el) => {
      observer.observe(el)
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

/* ABOUT PAGE */
.about {
  min-height: 100vh;
  padding-top: 10rem;
  background: linear-gradient(135deg, #f9fcff 0%, #f0f5ff 50%, #e6eeff 100%);
  position: relative;
  overflow: hidden;
  font-family: 'TikTok Sans', sans-serif;
}

/* Formas decorativas flutuantes */
.bg-shape {
  position: absolute;
  opacity: 0.12;
  pointer-events: none;
  z-index: 0;
  animation: float 25s infinite ease-in-out;
}

.shape-circle-1 {
  width: 700px;
  height: 700px;
  background: radial-gradient(circle, #0a07da 0%, transparent 70%);
  top: 10%;
  right: -150px;
  border-radius: 50%;
}

.shape-circle-2 {
  width: 600px;
  height: 600px;
  background: radial-gradient(circle, #0c0a69 0%, transparent 65%);
  top: 50%;
  left: -200px;
  border-radius: 50%;
  animation-delay: -12s;
}

.shape-circle-3 {
  width: 500px;
  height: 500px;
  background: radial-gradient(circle, #0a07da 0%, transparent 75%);
  bottom: 15%;
  right: -100px;
  border-radius: 50%;
  animation-delay: -8s;
}

.shape-line-1 {
  width: 800px;
  height: 4px;
  background: linear-gradient(to right, transparent, #0a07da, transparent);
  top: 35%;
  left: -200px;
  transform: rotate(20deg);
  animation-delay: -15s;
}

.shape-line-2 {
  width: 900px;
  height: 4px;
  background: linear-gradient(to right, transparent, #0c0a69, transparent);
  bottom: 30%;
  right: -250px;
  transform: rotate(-15deg);
  animation-delay: -20s;
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

/* Hero */
.about-hero {
  text-align: center;
  padding: 6rem 2rem;
  position: relative;
  z-index: 1;
  opacity: 0;
  transform: translateY(50px);
  transition: all 1.2s ease-out;
}

.about-hero.visible {
  opacity: 1;
  transform: translateY(0);
}

.lottie-hero {
  width: 380px;
  max-width: 90%;
  filter: drop-shadow(0 15px 40px rgba(10, 7, 218, 0.2));
  margin-bottom: 2rem;
}

.hero-title {
  font-size: 3.8rem;
  color: #333;
}

.hero-subtitle {
  font-size: 1.8rem;
  color: #0a07da;
  font-weight: 600;
}

/* Seções */
.about-sections {
  max-width: 1300px;
  margin: 0 auto;
  padding: 4rem 2rem;
  position: relative;
  z-index: 1;
}

.about-block {
  display: flex;
  align-items: center;
  margin: 8rem 0;
  min-height: 500px;
  position: relative;
}

.about-block.left {
  justify-content: flex-start;
}

.about-block.right {
  justify-content: flex-end;
}

.block-content {
  max-width: 620px;
  background: rgba(255, 255, 255, 0.98);
  backdrop-filter: blur(15px);
  padding: 3.5rem;
  border-radius: 32px;
  box-shadow: 0 25px 60px rgba(10, 7, 218, 0.15);
  border: 1px solid rgba(10, 7, 218, 0.08);
  opacity: 0;
  transition: all 1s ease-out;
}

.left .block-content {
  transform: translateX(-80px);
}

.right .block-content {
  transform: translateX(80px);
}

.about-block.visible .block-content {
  opacity: 1;
  transform: translateX(0);
}

.block-content h2 {
  font-size: 2.6rem;
  color: #0a07da;
  margin-bottom: 1.8rem;
  position: relative;
}

.block-content h2::after {
  content: '';
  position: absolute;
  width: 80px;
  height: 4px;
  background: linear-gradient(to right, #0a07da, transparent);
  bottom: -10px;
  left: 0;
}

.block-content p {
  font-size: 1.25rem;
  color: #444;
  line-height: 1.9;
  margin-bottom: 1.2rem;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 2rem;
}

.tech-tags span {
  background: linear-gradient(135deg, #e8e7ff, #f0f0ff);
  color: #0a07da;
  padding: 0.8rem 1.5rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1.05rem;
  box-shadow: 0 4px 15px rgba(10, 7, 218, 0.1);
}

/* Divisor */
.section-divider {
  height: 1px;
  background: linear-gradient(
    to right,
    transparent,
    #c0c8ff 30%,
    #0a07da 50%,
    #c0c8ff 70%,
    transparent
  );
  margin: 6rem auto;
  width: 80%;
  max-width: 800px;
  opacity: 0.6;
}

/* CTA Final */
.about-cta-block {
  text-align: center;
  padding: 8rem 2rem;
  opacity: 0;
  transform: translateY(60px);
  transition: all 1.2s ease-out;
}

.about-cta-block.visible {
  opacity: 1;
  transform: translateY(0);
}

.about-cta-block h2 {
  font-size: 3.2rem;
  color: #333;
  margin-bottom: 1.5rem;
}

.about-cta-block p {
  font-size: 1.6rem;
  color: #555;
  margin-bottom: 3.5rem;
}

.btn-contact-large {
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

.btn-contact-large:hover {
  transform: translateY(-12px);
  box-shadow: 0 30px 70px rgba(10, 7, 218, 0.4);
}

/* Animações */
.fade-in,
.fade-in-left .block-content,
.fade-in-right .block-content {
  opacity: 0;
}

.fade-in.visible,
.about-block.visible .block-content {
  opacity: 1;
}

/* RESPONSIVIDADE */
@media (max-width: 1024px) {
  .bg-shape {
    opacity: 0.08;
  }
}

@media (max-width: 968px) {
  .bg-shape {
    display: none;
  }

  .about-block {
    justify-content: center;
    margin: 6rem 0;
  }

  .left .block-content,
  .right .block-content {
    transform: translateY(60px);
    max-width: 85%;
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
    padding-top: 5rem;
    gap: 3.5rem;
    transform: translateX(100%);
    transition: transform 0.5s ease;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
  }

  nav ul.mobile-open {
    transform: translateX(0);
  }

  .about {
    padding-top: 8rem;
  }

  .lottie-hero {
    width: 300px;
  }

  .hero-title {
    font-size: 3rem;
  }

  .block-content {
    padding: 2.5rem;
  }

  .block-content h2 {
    font-size: 2.3rem;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 2.6rem;
  }

  .block-content h2 {
    font-size: 2.1rem;
  }

  .btn-contact-large {
    padding: 1.4rem 3rem;
    font-size: 1.3rem;
  }
}
</style>
