<template>
  <div class="third-column">
    <div class="helper">
      <div class="money" v-for="(item, index) in items" :key="index">
        <img :src="item.icon" alt="" />
        <p class="textpanel">{{ item.value }}</p>
      </div>
    </div>
  </div>
</template>
  
<script setup>
const items = [
  { icon: '/src/assets/svg/ph_coin-light.svg', value: '100' },
  { icon: '/img/svg/ant-design_fire-filled.svg', value: '100' },
  { icon: '/img/svg/material-symbols_favorite.svg', value: '100' },
];
</script>
  
<style scoped>
.third-column {
  width: 25%; /* Занимает 1/4 пространства */
  background-color: #d0d0d0;
  padding: 20px;
  box-sizing: border-box;
}

.helper {
  display: flex;
  gap: 20px;
  margin-top: 50px;
}

.money {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 8px 12px;
  border: 2px solid #8529CE;
  border-radius: 15px;
  background-color: white;
}

.money img {
  width: 24px;
  height: 24px;
}

.textpanel {
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  font-size: 16px;
  line-height: 1.5;
  color: #333;
}
</style>