<template>
  <button class="button" @click="clicado" :disabled="desabilitado">
    <span class="icon">
      <i :class="icone"></i>
    </span>
    <span>{{texto}}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "BotaoApp",
  emits: ['clicado'],
  props: {
    desabilitado: {
      type: Boolean
    },
    icone: {
      type: String,
      required: true
    },
    texto: {
      type: String,
      required: true
    },
  },
  methods: {
    clicado () : void {
      this.$emit('clicado')
    }
  }
});
</script>

<style scoped>
.button {
  background-color: white !important;
  color: #363636 !important;
  border: 1px solid #dbdbdb !important;
  box-shadow: none !important;
}

.button:hover {
  background-color: #f5f5f5 !important;
  border-color: #b5b5b5 !important;
}

.button:disabled {
  background-color: #f0f0f0 !important;
  color: #b5b5b5 !important;
  border-color: #e0e0e0 !important;
  cursor: not-allowed !important;
}
</style>
