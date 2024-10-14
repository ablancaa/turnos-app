<template>
    <div class="pantalla-turnos">
      <h1>Torn Actual</h1>
      <div v-if="turnoActual">
        <h2>Número de Torn: {{ turnoActual.numero }}</h2>
        <p>Nombre: {{ turnoActual.nombre }}</p>
      </div>
      <div v-else>
        <p>No hi ha torns actualment.</p>
      </div>
    </div>
</template>
  
<script setup>
import { defineProps } from 'vue';
  defineProps({
    turnoActual: Object
  });
  </script>
  
  <style scoped>
  /* Añadir estilos según preferencia */
  </style>
  
  