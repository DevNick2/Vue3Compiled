<template>
  <h1>Extraction and Reuse</h1>
  <p>
    {{ x }}
  </p>
  <button @click="setNameProps">Props Dinamic</button>
  <props-test :name="state.titleProps"/>
</template>

<script>
import PropsTest from './Props'

import { hello } from './CompositionApi'
import { reactive } from 'vue'

export default {
  components: {
    PropsTest
  },
  setup () {
    const state = reactive({
      titleProps: 'Um Nome comum'
    })
    // Reuse
    const { x } = hello()

    function setNameProps () {
      state.titleProps = 'Hello'
    }
    
    return {
      setNameProps,
      state,
      x
    }
  }
}
</script>

<style>

</style>