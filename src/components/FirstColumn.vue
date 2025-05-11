<template>
  <div class="sidebar-container">
    <!-- Кнопка меню для мобильных -->
    <button v-if="isMobile" @click="showSidebar = !showSidebar" class="mobile-menu-button">
      ☰ Меню
    </button>

    <!-- Боковая панель -->
    <div v-show="!isMobile || showSidebar" class="first-column">
      <p class="logo">
        <img :src="Skill" alt="lohs" class="logo-img">
      </p>

      <button
        v-for="button in buttons"
        :key="button.id"
        @click="handleClick(button.id)"
        class="menu-button"
      >
        {{ button.label }}
      </button>
    </div>

    <!-- Затемнение фона при открытом меню -->
    <div v-if="isMobile && showSidebar" @click="showSidebar = false" class="overlay"></div>
  </div>
</template>
<script setup>
import logoSkil from '@/assets/svg/skillmaster.svg';
import { ref, onMounted } from 'vue';

const Skill = ref(logoSkil);

const emit = defineEmits(['button-clicked']);

const buttons = ref([
  { id: 1, label: 'Тестирование' },
  { id: 2, label: 'Разделы' },
  { id: 3, label: 'Рейтинг' },
  { id: 4, label: 'Магазин' },
  { id: 5, label: 'Профиль' },
  { id: 6, label: 'Еще' },
]);

const handleClick = (buttonId) => {
  emit('button-clicked', buttonId);
};

const isMobile = ref(false);
const showSidebar = ref(true);

// Определяем, мобильное ли устройство
const checkMobile = () => {
  isMobile.value = window.innerWidth <= 768;
};

onMounted(() => {
  checkMobile();
  window.addEventListener('resize', checkMobile);
});
</script>
  
  
<style scoped>
.sidebar-container {
  position: relative;
  flex-shrink: 0; /* Важно: панель не будет сжиматься */
}

.mobile-menu-button {
  display: none;
  padding: 10px 20px;
  font-size: 16px;
  margin-bottom: 10px;
  background-color: #8529CE;
  color: white;
  border: none;
  border-radius: 15px;
  cursor: pointer;
}

@media (max-width: 768px) {
  .mobile-menu-button {
    display: block;
  }
}

.first-column {
  width: 100%;
  max-width: 400px !important;
  background-color: white;
  padding: 20px;
  box-sizing: border-box;
  text-align: center;
}

.logo {
  margin-top: 10px;
  margin-bottom: 30px;
  text-align: center;
}

.logo-img {
  height: 60px;
  width: auto;
  max-width: 250px;
  object-fit: contain;
}

.menu-button {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  text-transform: uppercase;
  color: #8529CE;
  border: none;
  width: 100%;
  max-width: 305px;
  height: 60px;
  border-radius: 15px;
  padding: 16px 24px;
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(133, 41, 206, 0.1);
  transition: background-color 0.3s ease;
}

.menu-button:hover {
  background-color: rgba(133, 41, 206, 0.2);
}

.overlay {
  display: none;
}

/* === Стили для мобильных устройств === */
@media (max-width: 768px) {
  .first-column {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 999;
    background-color: white;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    transform: translateY(-100%);
    transition: transform 0.3s ease;
  }

  .first-column.active {
    transform: translateY(0);
  }

  .overlay {
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 998;
  }

  .logo {
    margin-bottom: 20px;
  }

  .menu-button {
    margin-bottom: 15px;
  }
}
</style>