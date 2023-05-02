<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <barra-lateral/>
    </div>
    <div class="column is-three-quarter">
      <formulario/>

    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from "@/components/BarraLateral.vue";
import Formulario from "@/components/formulario.vue";

export default defineComponent({
  name: 'App',
    components: {Formulario, BarraLateral}
});
</script>

