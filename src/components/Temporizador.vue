<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <cronometro :tempo-em-segundos="tempoEmSegundos"/>
        <button class="button" @click="iniciar" :disabled="cronometroRodando">
                            <span class="icon">
                                <i class="fas fa-play"></i>
                            </span>
            <span>play</span>
        </button>
        <button class="button" @click="finalizar" :disabled="!cronometroRodando">
                            <span class="icon">
                                <i class="fas fa-stop"></i>
                            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script>
import {defineComponent} from "vue";
import Cronometro from "@/components/Cronometro.vue";

export default defineComponent({
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Temporizador",
    components: {Cronometro},
    data () {
        return {
            tempoEmSegundos: 0,
            refenciaIntervalo: 0,
            cronometroRodando : false
        }
    },
    emits: ['aoTemporizadorFinalizado'],
    methods: {
    // eslint-disable-next-line @typescript-eslint/no-empty-function
    iniciar() {
        this.refenciaIntervalo = setInterval(() => { this.tempoEmSegundos++; }, 1000);
        this.cronometroRodando = true;
    },
    finalizar() {
        this.cronometroRodando = false;
        clearInterval(this.refenciaIntervalo);
        this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos);
        this.tempoEmSegundos = 0;
    }
}
})
</script>

<style scoped>

</style>