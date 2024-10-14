<template>
  <div id="app" class="app-container">
    <TurnoFormulario @nuevo-turno="agregarTurno" />
    
    <!-- Pantalla principal para mostrar el turno actual -->
    <PantallaTurnos :turnoActual="turnoActual" />

    <!-- Botón para atender el turno actual -->
    <button class="boton-atender" @click="atenderTurno" v-if="turnoActual">Atender Turno</button>

    <!-- Lista de todos los turnos -->
    <div class="lista-turnos" v-if="turnos.length > 0">
      <h2>Llista de Torns</h2>
      <ul>
        <li v-for="turno in turnos" :key="turno.numero" :class="{ 'turno-actual': turno === turnoActual.value }">
          <h3>Torn {{ turno.numero }}: {{ turno.nombre }}</h3>
        </li>
      </ul>
    </div>
    <div v-else>
      <p>No hi ha torns pendents.</p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import TurnoFormulario from './components/TurnoFormulario.vue';
import PantallaTurnos from './components/PantallaTurnos.vue';

const turnos = ref([]);  // Array para almacenar todos los turnos

// Computed para obtener el turno actual (el primero en la cola)
const turnoActual = computed(() => {
  return turnos.value.length > 0 ? turnos.value[0] : null;
});

// Función para agregar un nuevo turno
const agregarTurno = (nombre) => {
  const nuevoTurno = {
    numero: turnos.value.length + 1,  // Asigna un número incrementado
    nombre: nombre
  };
  turnos.value.push(nuevoTurno);  // Agrega el nuevo turno al array
};

// Función para atender el turno actual y eliminarlo de la lista
const atenderTurno = () => {
  if (turnos.value.length > 0) {
    turnos.value.shift();  // Elimina el primer turno
  }
};
</script>

<style scoped>
/* Estilos generales */
.app-container {
  font-family: Arial, sans-serif;
  text-align: center;
  padding: 20px;
  max-width: 600px;
  margin: 0 auto;
  background-color: #f4f4f9;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
  margin-top: 20px;
  font-size: 1.5rem;
  color: #333;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  background-color: #fff;
  padding: 10px;
  margin: 5px 0;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: background-color 0.3s ease;
}

.turno-actual {
  background-color: #ffe6e6;  /* Fondo rojo claro */
  font-weight: bold;
  color: #d9534f;  /* Texto rojo */
}

.boton-atender {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: #5cb85c;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.boton-atender:hover {
  background-color: #4cae4c;
}

.lista-turnos {
  margin-top: 30px;
}

p {
  color: #777;
  font-size: 1rem;
}

/* Responsive Design */

/* Para pantallas pequeñas (móviles, menos de 600px) */
@media (max-width: 600px) {
  .app-container {
    padding: 10px;
    max-width: 90%;
  }

  h2 {
    font-size: 1.2rem;
  }

  .boton-atender {
    font-size: 0.9rem;
    padding: 8px 16px;
  }

  li {
    padding: 8px;
  }
}

/* Para pantallas medianas (tablets, entre 600px y 1024px) */
@media (min-width: 600px) and (max-width: 1024px) {
  .app-container {
    max-width: 80%;
  }

  h2 {
    font-size: 1.4rem;
  }

  .boton-atender {
    font-size: 1rem;
    padding: 10px 18px;
  }

  li {
    padding: 10px;
  }
}

/* Para pantallas grandes (escritorio, más de 1024px) */
@media (min-width: 1024px) {
  .app-container {
    max-width: 70%;
  }
}
</style>


