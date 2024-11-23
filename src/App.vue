<template>
  <div>
    <EmisorComponent />
    <ReceptorComponent receptorId="1" />
    <ReceptorComponent receptorId="2" />
  </div>
</template>

<script>
import EmisorComponent from './components/EmisorComponent.vue';
import ReceptorComponent from './components/ReceptorComponent.vue';

export default {
  components: {
    EmisorComponent,
    ReceptorComponent,
  },
};
</script>
