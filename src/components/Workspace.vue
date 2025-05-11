<template>
  <div class="workspace">
    <!-- Кнопка для управления третьей колонкой -->
    <button class="toggle-third-column" @click="toggleThirdColumn">
      {{ showThirdColumn ? 'x' : '<' }}
    </button>

    <FirstColumn @button-clicked="handleButtonClick" />
    <SecondColumn :width="secondColumnWidth" :activeComponent="activeComponent" />
    <ThirdColumn v-if="showThirdColumn" @hide="hideThirdColumn" />
  </div>
</template>

<script setup>
import FirstColumn from './FirstColumn.vue';
import SecondColumn from './SecondColumn.vue';
import ThirdColumn from './ThirdColumn.vue';
import {ref, computed} from 'vue';
const components = ref({
    FirstColumn,
    SecondColumn,
    ThirdColumn
});
const showThirdColumn = ref(false);
const activeComponent = ref( null);
const secondColumnWidth = computed(()=> {return showThirdColumn.value ? '50%' : '75%'});
const handleButtonClick=(buttonId) => {
  const componentMap = {
        1: 'ComponentOne',
        2: 'ComponentTwo',
        3: 'ComponentThree',
        4: 'ComponentFour',
        5: 'ComponentFive',
        7: 'ComponentTest',
      };
      activeComponent.value = componentMap[buttonId] || null;
};
const toggleThirdColumn = ()=> {
  showThirdColumn.value=!showThirdColumn.value;
};
const hideThirdColumn = ()=> {
  showThirdColumn=false;
};

</script>



<style scoped>
.workspace {
  display: flex;
  width: 100%;
  min-height: 100vh;
  position: relative;
  background-color: #f5f5f5;
  display: flex;
  width: 100%;
  min-height: 100vh;
}

/* === Кнопка для управления третьей колонкой === */
.toggle-third-column {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 100;
  padding: 10px 16px;
  font-size: 18px;
  background-color: #8529CE;
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.toggle-third-column:hover {
  background-color: #7020b0;
}
</style>