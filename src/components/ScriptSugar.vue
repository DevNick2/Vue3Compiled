<template>
  <h1>Composition API Syntax Sugar</h1>

  <div>
    <p> {{ computedMsg }} </p>
  </div>
</template>

<script setup="props">
import { computed } from 'vue'

export default {
  props: {
    msg: String
  },
  // Herda os atributos do componente pai
  // inheritAttrs: false || true
}

export const computedMsg = computed(() => props.msg + ' World ')
</script>

<style>

</style>