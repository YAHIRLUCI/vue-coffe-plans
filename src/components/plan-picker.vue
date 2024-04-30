<template>
    <div ref="plansWrapper" style="border:red double 10px;" @click="select" class="plans">
      <plan-picker-item
      @select="printSelected"
      :selectedPlan="selectedPlan"
      v-for="plan in plans" 
      :name="plan"
      v-bind:key="plan" />
      <p style="font-size: 30px;">counter: {{ counter }}</p>
    </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted  } from 'vue';
import planPickerItem from './plan-picker-item.vue';
const plans = ref([
  "El soltero",
  "El adicto",
  "El viajero",
  "El colombiano",
  "El italiano"]);
 const plansWrapper = ref (null);
 const selectedPlan = ref(null);


  const printSelected = (playload) => {
   selectedPlan.value =playload;
  }

  //creando una referencia reactiva contador
  const counter = ref(0);
  //creando un metodo para incrementar el comtador
  setInterval(()=>{
    counter.value++;
  },1000);
  //obtener la referencia del elemento plans
 const data = document.querySelector('.plans');
 console.log(data);
  //registrandoi el CB(call Back)onMounted
  onMounted(()=>{
 console.log(plansWrapper.value);
  });
  onUnmounted(()=>{
 console.log('componente Plan Picker desmontar');
  });

  </script>