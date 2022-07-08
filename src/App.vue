<template>
  <div>
    <vFor />
    <vModel />
    <vIf />
    <vBind />
  </div>
</template>

<script>
import vFor from './components/directives/vFor.vue'
import vModel from './components/directives/vModel.vue'
import vIf from './components/directives/vIf.vue'
import vBind from './components/directives/vBind.vue'

export default {
  name: 'App',
  components: {
    vFor,
    vModel,
    vIf,
    vBind
  }
}
</script>

<style></style>
