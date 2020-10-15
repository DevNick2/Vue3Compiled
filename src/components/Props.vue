<template>
  <h1>Props in Setup</h1>
  <p>
    Props: {{ state.name }}
  </p>
</template>

<script>
import { reactive, watchEffect } from 'vue'
export default {
  props: {
    name: {
      type: [String],
      default: ''
    }
  },
  setup (props) {
    const state = reactive({
      name: ''
    })

    watchEffect(() => {
      console.log('Name + ', props.name)
      state.name = props.name
    })

    return {
      state
    }
  }
}
</script>

<style>

</style>