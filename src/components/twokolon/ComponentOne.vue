<template>
    <div class="testing-container">
      <p class="info-text">Здесь вы можете пройти тестирования, которые помогут лучше определить программу и прогресс вашего обучения</p>
      
      <div class="test-buttons">
        <button @click="handleClick(7)" class="test-button beginner">
          <div class="button-content">
            <p class="button-title">Начальное тестирование</p>
            <div class="button-details">
              <div class="test-type">ПРОВЕРКА УРОВНЯ НАЧАЛЬНЫХ НАВЫКОВ</div>
              <div class="test-info">
                <span class="info-badge">33 ВОПРОСА</span>
                <span class="info-badge">МАКСИМУМ БАЛЛОВ 165</span>
              </div>
            </div>
          </div>
        </button>
  
        <button class="test-button final">
          <div class="button-content">
            <p class="button-title">ФИНАЛЬНОЕ ТЕСТИРОВАНИЕ</p>
            <div class="button-details">
              <div class="test-type">ПРОВЕРКА ПРОКАЧЕННЫХ НАВЫКОВ</div>
              <div class="test-info">
                <span class="info-badge">33 ВОПРОСА</span>
                <span class="info-badge">МАКСИМУМ БАЛЛОВ 165</span>
              </div>
            </div>
          </div>
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const emit = defineEmits(['button-clicked']);
  
  const handleClick = (buttonId) => {
    emit('button-clicked', buttonId);
  }
  </script>
  
  <style scoped>
  .testing-container {
    max-width: 1200px;
    width: 100%;
    margin: 0 auto;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
  }
  
  .info-text {
    background: #8529ce;
    border-radius: 25px;
    color: #ffffff;
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 16px;
    line-height: 1.5;
    text-align: center;
    text-transform: uppercase;
    padding: 20px;
    margin-bottom: 30px;
    width: 100%;
    max-width: 611px;
    box-sizing: border-box;
  }
  
  .test-buttons {
    display: flex;
    flex-direction: column;
    gap: 30px;
    width: 100%;
    max-width: 611px;
  }
  
  .test-button {
    width: 100%;
    background: #e66385;
    border: none;
    border-radius: 25px;
    padding: 0;
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 0 rgba(0, 0, 0, 0.2);
  }
  
  .test-button:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 0 rgba(0, 0, 0, 0.2);
  }
  
  .test-button:active {
    transform: translateY(1px);
    box-shadow: 0 2px 0 rgba(0, 0, 0, 0.2);
  }
  
  .button-content {
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 15px;
  }
  
  .button-title {
    color: #ffffff;
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 24px;
    line-height: 1.3;
    text-transform: uppercase;
    margin: 0;
    text-align: left;
  }
  
  .button-details {
    background: #ffffff;
    border-radius: 25px;
    padding: 15px;
    width: 100%;
    box-sizing: border-box;
  }
  
  .test-type {
    font-family: 'Montserrat', sans-serif;
    border: 1px solid #000000;
    border-radius: 25px;
    padding: 8px;
    text-align: center;
    margin-bottom: 10px;
    font-size: 14px;
  }
  
  .test-info {
    display: flex;
    justify-content: space-between;
    gap: 10px;
  }
  
  .info-badge {
    border: 1px solid #000000;
    border-radius: 25px;
    padding: 8px;
    font-family: 'Montserrat', sans-serif;
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex: 1;
  }

  @media (max-width: 768px) {
  .testing-container {
    padding: 15px;
  }

  .info-text {
    font-size: 14px;
    padding: 15px;
    border-radius: 20px;
  }

  .test-buttons {
    gap: 20px;
  }

  .button-title {
    font-size: 20px;
  }

  .button-content {
    padding: 15px;
  }

  .button-details {
    padding: 12px;
  }

  .test-type,
  .info-badge {
    font-size: 12px;
    border-radius: 20px;
  }

  .test-info {
    flex-wrap: wrap;
  }

  .info-badge {
    flex: 1 1 100%;
    text-align: center;
  }
}

@media (max-width: 480px) {
  .info-text {
    font-size: 12px;
    border-radius: 15px;
    padding: 10px;
  }

  .test-button {
    border-radius: 15px;
  }

  .button-title {
    font-size: 18px;
  }

  .button-content {
    padding: 12px;
  }

  .button-details {
    padding: 10px;
    border-radius: 15px;
  }

  .test-type,
  .info-badge {
    font-size: 11px;
    border-radius: 15px;
  }

  .test-info {
    gap: 5px;
  }

  .info-badge {
    flex: 1 1 100%;
  }
}
</style>