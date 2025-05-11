<template>
    <div id="app">
      <router-view />
    </div>
  </template>
  
  <script>
  export default {
    name: 'App'
  };
  </script>
  
  <style>
  /* Базовые глобальные стили */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  html {
    font-size: 16px;
    scroll-behavior: smooth;
  }
  
  body {
    font-family: 'Montserrat', sans-serif;
    min-height: 100vh;
    margin: 0;
    padding: 0;
    background-color: #f5f5f5;
    color: #333;
    overflow-x: hidden; /* Запрещаем горизонтальный скролл */
  }
  
  #app {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    overflow-y: auto;
    -webkit-overflow-scrolling: touch;
  }
  
  /* Контейнер для всех страниц */
  .container {
    max-width: 1200px;
    width: 100%;
    padding: 0 20px;
    margin: 0 auto;
    text-align: left;
  }
  
  @media (max-width: 768px) {
    .container {
      padding: 0 15px;
    }
  }
  </style>