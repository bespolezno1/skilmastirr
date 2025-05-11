<template>
    <div class="second-column" :style="{ width: width }">
      <!-- Динамический компонент -->
      <transition name="fade">
        <component
        v-if="component[props.activeComponent]"
        :is="component[props.activeComponent]"
      />
        <ComponentOne v-else />
        
        
      </transition>
      
    </div>
  </template>
  
  <script setup>
  import ComponentOne from './twokolon/ComponentOne.vue';
  import ComponentTwo from './twokolon/ComponentTwo.vue';
  import ComponentThree from './twokolon/ComponentThree.vue';
  import ComponentFour from './twokolon/ComponentFour.vue';
  import ComponentFive from './twokolon/ComponentFive.vue';
  import ComponentTest from './twokolon/ComponentTest.vue';
  import { defineProps } from 'vue';
  const props = defineProps({
    width: {
        type: String,
        required: true
      },
      activeComponent: {
        type: String,
        required: true
      }
  });
  const component = {
    ComponentOne,
    ComponentTwo,
    ComponentThree,
    ComponentFour,
    ComponentFive,
    ComponentTest,

  }
  

  </script>
  
  
  
  <style scoped>
  .second-column {
    background-color: white;
    padding: 20px;
    box-sizing: border-box;
    transition: width 0.3s ease; /* Анимация изменения ширины */
    width: 695px;
    height: 900px;
  }
  </style>