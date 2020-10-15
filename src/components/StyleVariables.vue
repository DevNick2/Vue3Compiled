<template>
  <h1>Style with variables in attrs</h1>
  <button @click="onChangeColor">Change Color</button>
  <div class="test"></div>
</template>

<script lang="ts">
import { reactive, computed } from 'vue'

export default {
  setup () {
    const state = reactive({
      boxColor: '#9c27b0'
    })
    
    function onChangeColor () {
      state.boxColor = '#ff5722'
    }

    const color = computed(() => state.boxColor)
    return {
      onChangeColor,
      color
    }
  }
}
</script>

<style scoped vars="{ color }">
.test {
  background: var(--color);
  width: 50px;
  height: 50px;
}
</style>