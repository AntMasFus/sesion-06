<template>
    <div v-if="mostrarMensaje">
      <h3>Receptor {{ receptorId }}</h3>
      <p>{{ mensaje }}</p>
    </div>
  </template>
  
  <script>
  import { eventBus } from '../eventBus';
  import { computed, watch } from 'vue';
  
  export default {
    props: {
      receptorId: {
        type: String,
        required: true,
      },
    },
    setup(props) {
      const mensaje = computed(() => eventBus.message?.contenido || '');
      const mostrarMensaje = computed(() => eventBus.message?.id === props.receptorId);
  
      return {
        mensaje,
        mostrarMensaje,
      };
    },
  };
  </script>
  