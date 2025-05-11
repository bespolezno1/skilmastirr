<template>
  <div class="home">
    <header class="header">
      <div class="wrapper">
        <div class="header_wrapper">
          <div class="header_text">
            <a href="index.html" class="header_name">SKILLMASTER</a>
          </div>

          <button class="mobile-menu-btn" @click="toggleMenu">
            <span></span>
            <span></span>
            <span></span>
          </button>

          <nav class="header_nav" :class="{ 'active': isMenuOpen }">
            <ul class="header_list">
              <li class="header_item">
                <a href="#!" class="header_link">О НАС</a>
              </li>
              <li class="header_item">
                <a href="#!" class="header_link">ЦЕНЫ</a>
              </li>
              <li class="header_item">
                <a href="#!" class="header_link">СКАЧАТЬ СЕЙЧАС</a>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </header>

    <main class="main">
      <section class="fon_skill">
        <div class="wrapper">
          <div class="logo_skill">
            <img :src="imageLogo" alt="Skillmaster Logo">
          </div>
          <p class="intro_subtext">
            ИГРАЙ И РАЗВИВАЙ ГИБКИЕ НАВЫКИ ПРЯМО В СВОЕМ ТЕЛЕФОНЕ
          </p>
          <div class="vibor">
            <button @click="navigateToRegister" class="button button_redy">НАЧАТЬ СЕЙЧАС</button>
            <button @click="navigateToLogin" class="button button_now">УЖЕ ЕСТЬ АККАУНТ</button>
          </div>
          <p class="golov">
            <img :src="golova" alt="Иллюстрация">
          </p>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import logo from '@/assets/svg/skillmaster.svg';
import { ref } from 'vue';
const imageLogo = ref(logo);
import logG from '@/assets/svg/Frame_198.svg';
const golova = ref(logG);

const isMenuOpen = ref(false);
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<script>
export default {
  methods: {
    navigateToLogin() {
      this.$router.push('/login');
    },
    navigateToRegister() {
      this.$router.push('/register');
    }
  }
};
</script>
  
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');

/* Базовые стили */
.wrapper {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 20px;
}

.header {
  background-color: rgba(142, 56, 210, 1);
  min-height: 60px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
}

.header_wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 80px;
  margin: 0 auto;
  height: 77px;
}

.header_name {
  font-family: 'Montserrat', sans-serif;
  font-size: 20px;
  font-weight: 600;
  color: #ffffff;
  text-decoration: none;
}

.mobile-menu-btn {
  display: none;
  background: transparent;
  border: none;
  width: 30px;
  height: 20px;
  flex-direction: column;
  justify-content: space-between;
  cursor: pointer;
  z-index: 101;
}

.mobile-menu-btn span {
  display: block;
  width: 100%;
  height: 3px;
  background: white;
  transition: all 0.3s ease;
}

.header_nav {
  transition: all 0.3s ease;
}

.header_list {
  display: flex;
  gap: 20px;
}

.header_link {
  font-size: 14px;
  font-weight: 600;
  color: #ffffff;
  text-decoration: none;
  font-family: 'Montserrat', sans-serif;
}

.header_link:hover {
  opacity: 0.75;
}

.main {
  width: 100%;
  padding: 80px 0 40px;
  margin-top: 60px;
}

.logo_skill {
  padding-top: 40px;
  margin-bottom: 30px;
}

.logo_skill img {
  max-width: 100%;
  height: auto;
}

.intro_subtext {
  font-weight: 500;
  font-size: 32px;
  line-height: 1.3;
  color: #000000;
  margin-bottom: 30px;
  font-family: 'Montserrat', sans-serif;
  text-align: center;

  /* Добавляем фон и внутренние отступы */
  display: inline-block;
  padding: 15px 20px;
  border-radius: 30px;
  background: linear-gradient(90deg, rgba(255, 255, 255, 0.7) 0%, rgba(255, 255, 255, 0.3) 100%);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
}

.vibor {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-bottom: 30px;
  align-items: center;
}

.button {
  display: block;
  width: 100%;
  max-width: 400px; /* Увеличили максимальную ширину */
  padding: 18px 24px; /* Больше внутреннего пространства */
  border-radius: 30px; /* Сделали углы чуть мягче */
  font-family: 'Montserrat', sans-serif;
  font-weight: 600; /* Жирный шрифт для лучшей читаемости */
  font-size: 18px; /* Увеличили размер текста */
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1); /* Лёгкая тень для объёма */
}

.button_redy {
  color: white;
  background: #9E56D8;
  border: 2px solid #8529CE;
}

.button_redy:hover {
  background: #8529CE;
}

.button_now {
  color: #8529CE;
  background: #FFFFFF;
  border: 2px solid #8529CE;
}

.button_now:hover {
  background-color: #f0f0ff;
}

.golov {
  display: none;
}
@media (max-width: 1024px) {
  .header_wrapper {
    padding: 0 40px;
  }

  .intro_subtext {
    font-size: 28px;
  }
}

@media (max-width: 768px) {
  .header_wrapper {
    padding: 0 20px;
  }

  .mobile-menu-btn {
    display: flex;
  }

  .header_nav {
    position: fixed;
    top: 60px;
    left: 0;
    width: 100%;
    background-color: rgba(142, 56, 210, 0.95);
    padding: 20px;
    transform: translateY(-100%);
    opacity: 0;
    pointer-events: none;
  }

  .header_nav.active {
    transform: translateY(0);
    opacity: 1;
    pointer-events: auto;
  }

  .header_list {
    flex-direction: column;
    gap: 15px;
    align-items: center;
  }

  .main {
    padding: 70px 0 30px;
  }

  .logo_skill {
    padding-top: 20px;
    margin-bottom: 20px;
  }

  .intro_subtext {
    font-size: 20px;
    margin-bottom: 20px;
  }

  .button {
    max-width: 100%;
    font-size: 14px;
    padding: 10px;
  }

  .golov {
    display: none;
  }
}

@media (min-width: 769px) {
  .golov {
    display: block;
    position: absolute;
    left: 60%;
    top: 75%;
    transform: translateY(-50%);
    width: 40%;
    max-width: 571px;
    height: auto;
  }

  .logo_skill img {
    width: auto;
    max-height: 132px;
  }

  .intro_subtext {
    width: 50%;
  }

  .vibor {
    width: 50%;
  }
}
</style>