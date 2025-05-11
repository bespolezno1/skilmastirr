<template>
  <div class="login-page">
    <!-- Кнопка регистрации -->
    <button @click="registBut" class="register-button">Регистрация</button>

    <!-- Основной контейнер формы -->
    <div class="login-container">
      <h1 class="login-title">Вход</h1>

      <form @submit.prevent="handleLogin" class="login-form">
        <input v-model="user.username" type="text" placeholder="Почта / Номер телефона" class="login-input">
        <input v-model="user.password" type="password" placeholder="Пароль" class="login-input">
        <button type="submit" class="login-button">Войти</button>
      </form>

      <p class="login-forgot">
        Забыли пароль? <a href="#">Восстановить</a>
      </p>
    </div>

    <!-- Декоративные эллипсы -->
    <div class="ellipses-container top-left">
      <div class="ellipse"></div>
      <div class="ellipse"></div>
      <div class="ellipse"></div>
    </div>
    <div class="ellipses-container bottom-right">
      <div class="ellipse"></div>
      <div class="ellipse"></div>
      <div class="ellipse"></div>
    </div>
  </div>
</template>
  

<script setup>
import router from '@/router';
import { ref } from 'vue';

const user = ref({
  username: '',
  password: ''
});

function handleLogin() {
  if (!user.value.username || !user.value.password) {
    alert('Заполните все поля');
    return;
  }
  alert('Вы вошли как ' + user.value.username);
  router.push('/workspace');
}

const registBut = () => {
  router.push('/Register');
};
</script>

  
  
<style scoped>
.login-page {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  overflow-x: hidden;
  background-color: #f5f5f5;
}

.register-button {
  position: fixed;
  top: 24px;
  right: 24px;
  width: auto;
  min-width: 200px;
  height: 50px;
  border-radius: 15px;
  border: 1px solid #ccc;
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 18px;
  color: #8529CE;
  background-color: white;
  cursor: pointer;
  z-index: 10;
}

.register-button:hover {
  background-color: #f0f0f0;
}

.login-container {
  text-align: center;
  max-width: 500px;
  width: 100%;
  margin-bottom: 40px;
  z-index: 1;
}

.login-title {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 32px;
  color: #8529CE;
  margin-bottom: 30px;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-bottom: 30px;
}

.login-input {
  width: 100%;
  padding: 16px 24px;
  border-radius: 15px;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  color: rgba(0, 0, 0, 0.5);
  background-color: rgba(151, 103, 198, 0.15);
  border: none;
  outline: none;
}

.login-button {
  width: 100%;
  padding: 16px 24px;
  border-radius: 15px;
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 16px;
  color: white;
  background-color: #8529CE;
  border: none;
  cursor: pointer;
}

.login-button:hover {
  background-color: #7020b0;
}

.login-forgot {
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
  color: #000;
}

.login-forgot a {
  color: #8529CE;
  text-decoration: underline;
  text-decoration-style: solid;
}
@media (max-width: 768px) {
  .login-title {
    font-size: 28px;
  }

  .login-input,
  .login-button {
    font-size: 14px;
    padding: 12px 16px;
  }

  .login-forgot {
    font-size: 14px;
  }

  .register-button {
    font-size: 16px;
    height: 45px;
    min-width: 160px;
  }
}

@media (max-width: 480px) {
  .login-title {
    font-size: 24px;
  }

  .login-input,
  .login-button {
    font-size: 14px;
    padding: 10px 14px;
  }

  .login-forgot {
    font-size: 13px;
  }

  .register-button {
    font-size: 14px;
    height: 40px;
    min-width: 140px;
  }
}
</style>