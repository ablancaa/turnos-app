<template>
    <div class="form-container">
      <h2>Demanar Torn</h2>
      <form @submit.prevent="enviarTurno">
        <input
          v-model="nombre"
          type="text"
          placeholder="Posa el teu nom"
          class="input-nombre"
          required
        />
        <button type="submit" class="boton-enviar">Demanar Torn</button>
      </form>
    </div>
</template>
  
<script setup>
  import { ref, defineEmits } from 'vue';
  
  const nombre = ref('');
  const emit = defineEmits(['nuevo-turno']);
  // Emite el evento 'nuevo-turno' al componente padre con el nombre ingresado
  const enviarTurno = () => {
    if (nombre.value.trim()) {
      // Emitimos el nombre al componente padre
      emit('nuevo-turno', nombre.value);
      nombre.value = ''; // Limpiamos el campo de nombre
    }
  };
</script>
  
<style scoped>
  /* Estilos generales del formulario */
  .form-container {
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 20px;
  }
  
  h2 {
    font-size: 1.5rem;
    color: #333;
    margin-bottom: 15px;
  }
  
  form {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  
  .input-nombre {
    padding: 10px;
    font-size: 1rem;
    border-radius: 5px;
    border: 1px solid #ccc;
    /*width: 100%;*/
  }
  
  .boton-enviar {
    padding: 10px;
    font-size: 1rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .boton-enviar:hover {
    background-color: #0056b3;
  }
  
  /* Responsive Design */
  
  /* Pantallas pequeñas (móviles) */
  @media (max-width: 600px) {
    .form-container {
      padding: 15px;
    }
  
    h2 {
      font-size: 1.2rem;
    }
  
    .input-nombre {
      font-size: 0.9rem;
      padding: 8px;
    }
  
    .boton-enviar {
      font-size: 0.9rem;
      padding: 8px;
    }
  }
  
  /* Pantallas medianas (tablets) */
  @media (min-width: 600px) and (max-width: 1024px) {
    .form-container {
      padding: 18px;
    }
  
    h2 {
      font-size: 1.3rem;
    }
  
    .input-nombre {
      font-size: 1rem;
      padding: 10px;
    }
  
    .boton-enviar {
      font-size: 1rem;
      padding: 10px;
    }
  }
  
  /* Pantallas grandes (escritorio) */
  @media (min-width: 1024px) {
    .form-container {
      padding: 20px;
    }
  
    h2 {
      font-size: 1.5rem;
    }
  
    .input-nombre {
      font-size: 1rem;
      padding: 12px;
    }
  
    .boton-enviar {
      font-size: 1rem;
      padding: 12px;
    }
  }
</style>
  