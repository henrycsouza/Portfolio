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

  <section class="contact-page">
    <!-- Formas decorativas -->
    <div class="bg-shape shape-circle-1"></div>
    <div class="bg-shape shape-circle-2"></div>
    <div class="bg-shape shape-line-1"></div>

    <div class="contact-container">
      <div class="contact-header fade-in">
        <h1>Entre em Contato</h1>
        <p>
          Gostou do meu trabalho? Tem um projeto em mente ou quer bater um papo
          sobre tecnologia?
        </p>
        <p>Preencha o formulário abaixo que eu respondo rapidinho!</p>
      </div>

      <div class="contact-content">
        <!-- Formulário FUNCIONAL com EmailJS -->
        <form class="contact-form fade-in-up" @submit.prevent="sendMessage">
          <div class="form-group">
            <label for="name">Nome *</label>
            <input
              type="text"
              id="name"
              v-model="form.name"
              required
              placeholder="Seu nome completo"
            />
          </div>

          <div class="form-group">
            <label for="email">E-mail *</label>
            <input
              type="email"
              id="email"
              v-model="form.email"
              required
              placeholder="seu@email.com"
            />
          </div>

          <div class="form-group">
            <label for="message">Mensagem *</label>
            <textarea
              id="message"
              v-model="form.message"
              required
              rows="8"
              placeholder="Conte-me sobre seu projeto, ideia ou oportunidade..."
            ></textarea>
          </div>

          <button type="submit" class="btn-send" :disabled="sending">
            {{ sending ? 'Enviando...' : 'Enviar Mensagem' }}
          </button>

          <!-- Mensagens de status -->
          <div v-if="success" class="success-message">
            <p>
              ✅ Mensagem enviada com sucesso! Entrarei em contato em breve.
              Obrigado!
            </p>
          </div>
          <div v-if="error" class="error-message">
            <p>
              ❌ Erro ao enviar. Tente novamente ou me mande direto no e-mail
              abaixo.
            </p>
          </div>
        </form>

        <!-- Redes sociais e e-mail direto -->
        <div class="contact-social fade-in-up">
          <h2>Ou me encontre aqui</h2>
          <div class="social-links">
            <a
              href="https://github.com/henrycsouza"
              target="_blank"
              rel="noopener"
              class="social-link"
            >
              <svg
                width="30"
                height="30"
                viewBox="0 0 24 24"
                fill="currentColor"
              >
                <path
                  d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                />
              </svg>
              GitHub
            </a>

            <a
              href="https://www.linkedin.com/in/henrycsouza/"
              target="_blank"
              rel="noopener"
              class="social-link"
            >
              <svg
                width="30"
                height="30"
                viewBox="0 0 24 24"
                fill="currentColor"
              >
                <path
                  d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                />
              </svg>
              LinkedIn
            </a>
          </div>

          <p class="contact-email">
            Ou envie direto:
            <a href="mailto:seuemail@gmail.com">henrycsouza2@gmail.com</a>
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import emailjs from '@emailjs/browser'

const mobileMenuOpen = ref(false)
const isScrolled = ref(false)
const sending = ref(false)
const success = ref(false)
const error = ref(false)

const form = ref({
  name: '',
  email: '',
  message: ''
})

const closeMenu = () => {
  mobileMenuOpen.value = false
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const sendMessage = async () => {
  if (!form.value.name || !form.value.email || !form.value.message) return

  sending.value = true
  success.value = false
  error.value = false

  try {
    await emailjs.send(
      'service_kxhc109', // ← SUBSTITUA
      'template_8z1hrr4', // ← SUBSTITUA
      {
        user_name: form.value.name,
        user_email: form.value.email,
        message: form.value.message
      },
      'O2TUbpWUh0VXW9hjI'
    )

    success.value = true
    form.value = { name: '', email: '', message: '' }
  } catch (err) {
    console.error(err)
    error.value = true
  } finally {
    sending.value = false

    // Limpa mensagens após 8 segundos
    setTimeout(() => {
      success.value = false
      error.value = false
    }, 8000)
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)

  const elements = document.querySelectorAll('.fade-in, .fade-in-up')
  elements.forEach((el, index) => {
    setTimeout(() => {
      el.style.opacity = 1
      el.style.transform = 'translateY(0)'
    }, index * 150)
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

/* NAVBAR (igual às outras páginas) */
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

/* CONTACT PAGE */
.contact-page {
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

.contact-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 4rem 2rem;
  position: relative;
  z-index: 1;
}

.contact-header {
  text-align: center;
  margin-bottom: 5rem;
  opacity: 0;
  transform: translateY(50px);
  transition: all 1.2s ease-out;
}

.contact-header.visible {
  opacity: 1;
  transform: translateY(0);
}

.contact-header h1 {
  font-size: 3.5rem;
  color: #333;
  margin-bottom: 1.5rem;
}

.contact-header p {
  font-size: 1.4rem;
  color: #666;
  line-height: 1.8;
  margin-bottom: 1rem;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: start;
}

.contact-form {
  background: #fff;
  padding: 3.5rem;
  border-radius: 32px;
  box-shadow: 0 20px 50px rgba(10, 7, 218, 0.12);
  opacity: 0;
  transform: translateY(60px);
  transition: all 1s ease-out;
}

.contact-form.visible {
  opacity: 1;
  transform: translateY(0);
}

.form-group {
  margin-bottom: 2rem;
}

.form-group label {
  display: block;
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 0.8rem;
  font-weight: 600;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1.2rem 1.5rem;
  border: 2px solid #e0e0ff;
  border-radius: 16px;
  font-size: 1.1rem;
  font-family: inherit;
  background: #f8f8ff;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #0a07da;
  background: #fff;
  box-shadow: 0 0 0 4px rgba(10, 7, 218, 0.1);
}

.btn-send {
  width: 100%;
  padding: 1.4rem;
  background: linear-gradient(135deg, #0a07da, #0c0a69);
  color: #fff;
  font-size: 1.3rem;
  font-weight: 700;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.4s ease;
  box-shadow: 0 10px 30px rgba(10, 7, 218, 0.3);
}

.btn-send:hover:not(:disabled) {
  transform: translateY(-5px);
  box-shadow: 0 20px 50px rgba(10, 7, 218, 0.4);
}

.btn-send:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.success-message {
  margin-top: 2rem;
  padding: 1.5rem;
  background: #e8fff0;
  border: 2px solid #00d084;
  border-radius: 16px;
  color: #006633;
  text-align: center;
  font-weight: 600;
}

/* Redes sociais */
.contact-social {
  text-align: center;
  opacity: 0;
  transform: translateY(60px);
  transition: all 1s ease-out 0.3s;
}

.contact-social.visible {
  opacity: 1;
  transform: translateY(0);
}

.contact-social h2 {
  font-size: 2.4rem;
  color: #333;
  margin-bottom: 2.5rem;
}

.social-links {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 1.5rem;
  background: #fff;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  text-decoration: none;
  color: #333;
  font-size: 1.3rem;
  font-weight: 600;
  transition: all 0.4s ease;
}

.social-link:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 50px rgba(10, 7, 218, 0.15);
  color: #0a07da;
}

.social-link svg {
  transition: fill 0.3s ease;
}

.social-link:hover svg {
  fill: #0a07da;
}

.contact-email {
  font-size: 1.3rem;
  color: #666;
}

.contact-email a {
  color: #0a07da;
  text-decoration: none;
  font-weight: 600;
}

.contact-email a:hover {
  text-decoration: underline;
}

/* Animações */
.fade-in,
.fade-in-up {
  opacity: 0;
  transition: all 1s ease-out;
}

.fade-in.visible,
.fade-in-up.visible {
  opacity: 1;
  transform: translateY(0);
}

.fade-in-up {
  transform: translateY(60px);
}

/* RESPONSIVIDADE */
@media (max-width: 968px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 4rem;
  }

  .contact-form {
    padding: 3rem;
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

  .contact-page {
    padding-top: 8rem;
  }

  .contact-header h1 {
    font-size: 3rem;
  }
}

@media (max-width: 480px) {
  .contact-header h1 {
    font-size: 2.6rem;
  }

  .contact-form {
    padding: 2rem;
  }

  .btn-send {
    padding: 1.3rem;
    font-size: 1.2rem;
  }
}
</style>
