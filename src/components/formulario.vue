<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criacao de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa você deseka iniciar ?">

            </div>
            <div class="column">
                <temporizador/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";

export default defineComponent({
    name: "FormuLario",
    components: {Temporizador},
    data () {
      return {
          tempoEmSegundos: 0,
          refenciaIntervalo: 0,
      }
    }
})
</script>

<style scoped>

</style>