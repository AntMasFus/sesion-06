<template>
    <div>
      <h3>Emisor</h3>
      <input v-model="mensaje" placeholder="Escribe un mensaje" />
      <input v-model="id" placeholder="ID del receptor" />
      <button @click="enviarMensaje">Enviar Mensaje</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  import { eventBus } from '../eventBus';
  
  export default {
    setup() {
      const mensaje = ref('');
      const id = ref('');
  
      const enviarMensaje = () => {
        eventBus.message = { id: id.value, contenido: mensaje.value };
      };
  
      return {
        mensaje,
        id,
        enviarMensaje,
      };
    },
  };
  </script>
  