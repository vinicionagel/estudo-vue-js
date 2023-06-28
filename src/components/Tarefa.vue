<script lang="ts">
import {defineComponent, PropType} from "vue";
export default defineComponent({
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Tarefa',
    components: {
        Box,
        Cronometro,
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
})


import Cronometro from "@/components/Cronometro.vue";
import ITarefa from "@/interfaces/ITarefa";
import Box from "@/components/Box.vue";
// eslint-disable-next-line vue/no-export-in-script-setup


</script>
<template>
<box>
  <div class="columns">
    <div class="column is-7">
        {{tarefa.descricao || 'Tarefa Padrão'}}
    </div>
      <div class="column">
          <cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"></cronometro>
      </div>
  </div>
</box>
</template>