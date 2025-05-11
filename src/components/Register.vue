<template>
  <div class="register-page">
    <!-- Заголовок -->
    <h1 class="reg-title">Регистрация</h1>

    <!-- Форма регистрации -->
    <form @submit.prevent="handleRegister" class="reg-form">
      <input v-model="username" type="text" placeholder="Логин" class="reg-input">
      <input v-model="password" type="password" placeholder="Пароль" class="reg-input">
      <input v-model="email" type="email" placeholder="Почта" class="reg-input">
      <button type="submit" class="reg-button">Зарегистрироваться</button>
    </form>

    <!-- Декоративные эллипсы -->
    <div class="ellipse-container top-left">
      <div class="ellipse"></div>
      <div class="ellipse"></div>
      <div class="ellipse"></div>
    </div>
    <div class="ellipse-container bottom-right">
      <div class="ellipse"></div>
      <div class="ellipse"></div>
      <div class="ellipse"></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      email: '',
    };
  },
  methods: {
    handleRegister() {
      alert('Вы зарегистрировались как ' + this.username);
      this.$router.push('/login');
    }
  }
};
</script>

<style scoped>
.register-page {
  position: relative;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background-color: #f5f5f5;
  font-family: 'Montserrat', sans-serif;
}

.reg-title {
  font-weight: 700;
  font-size: 32px;
  color: #E66385;
  margin-bottom: 30px;
  text-align: center;
}

.reg-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 100%;
  max-width: 500px;
}

.reg-input {
  width: 100%;
  padding: 16px 24px;
  border-radius: 15px;
  font-size: 16px;
  font-family: 'Montserrat', sans-serif;
  color: rgba(0, 0, 0, 0.5);
  background-color: rgba(231, 60, 104, 0.2);
  border: none;
  outline: none;
}

.reg-input::placeholder {
  color: rgba(0, 0, 0, 0.5);
}

.reg-button {
  width: 100%;
  padding: 16px 24px;
  border-radius: 15px;
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 16px;
  color: white;
  background-color: #E66385;
  border: none;
  cursor: pointer;
}

.reg-button:hover {
  background-color: #d45575;
}
@media (max-width: 768px) {
  .reg-title {
    font-size: 28px;
  }

  .reg-input,
  .reg-button {
    font-size: 14px;
    padding: 12px 16px;
  }
}

@media (max-width: 480px) {
  .reg-title {
    font-size: 24px;
  }

  .reg-input,
  .reg-button {
    font-size: 14px;
    padding: 10px 14px;
  }
}
</style>