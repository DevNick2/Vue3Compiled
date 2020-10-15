<template>
  <!-- Fragment Example -->
  <composition-api/>
  <extraction-and-reuse/>
  <style-variables/>
  <script-sugar msg="Hello"/>
</template>

<script>
import CompositionApi from './components/CompositionApi'
import ExtractionAndReuse from './components/ExtractionAndReuse'
import StyleVariables from './components/StyleVariables'
import ScriptSugar from './components/ScriptSugar'

export default {
  components: {
    CompositionApi,
    ExtractionAndReuse,
    StyleVariables,
    ScriptSugar
  }
}
</script>