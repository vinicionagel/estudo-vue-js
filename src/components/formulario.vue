<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulario para criacao de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa você deseka iniciar ?" v-model="descricaoTarefa">

            </div>
            <div class="column">
                <temporizador @aoTemporizadorFinalizado="finalizarTarefa"/>
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
    emits: ['aoSalvarTarefa'],
    data () {
      return {
          descricaoTarefa: "",
          dados: []
      }
    },
    methods: {
        finalizarTarefa(tempoDecorrido: number) : void {
            this.$emit('aoSalvarTarefa',{
                duracaoEmSegundos: tempoDecorrido,
                descricao: this.descricaoTarefa
            })
            this.descricaoTarefa = "";
        }
    }
})
</script>

<style scoped>

</style>