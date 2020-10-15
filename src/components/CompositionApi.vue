<template>
  <h1>
    Composition API
  </h1>
  <p>
    {{ state.count }}
  </p>
  <p>
    {{ double }}
  </p>
  <p>
    {{ state.welcome }}
  </p>
  <p>
    {{ x }}
  </p>
  <button @click="increment"> Incremento </button>
  <button @click="welcome"> Bem vindo </button>
</template>

<script>
import { ref, computed, onMounted, onUnmounted, reactive, watchEffect } from 'vue'

// Extraction And Reuse
export function hello () {
  // Semelhante ao computed porém mutavel
  const x = ref()

  function update (e) {
    x.value = e.pageX
  }
  onMounted(() => {
    window.addEventListener('mousemove', update)
  })
  onUnmounted(() => {
    window.removeEventListener('mousemove', update)
  })

  return { x }
}
export default {
  setup () {
    const state = reactive({
      count: 0,
      welcome: 'Hello'
    })
    // Computed
    const double = computed(() => state.count * 2)
    // Watch
    watchEffect(() => {
      console.log('Watch', double.value)
    })

    // Ciclo de vida
    onMounted (() => {
      console.log('Componente montado')
      console.log(state.count)
    })
    
    // Metodos
    function increment () {
      state.count++
    }
    function welcome () {
      state.welcome += ' Bocó'
    }

    const { x } = hello()

    // Retorno
    return {
      x,
      welcome,
      increment,
      double,
      state
    }
  }
}
</script>

<style>

</style>