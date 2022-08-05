<template>
  <div class="container">
    <vFor />
    <vModel />
    <vIf />
    <vBind />
    <vPreAndvOnce />
    <vOn />
    <vHTML />
    <vText />
    <methods-vue />
    <comments />
    <computedProperties />
  </div>
</template>

<script>
// diretivas
import vFor from './components/directives/vFor.vue'
import vModel from './components/directives/vModel.vue'
import vIf from './components/directives/vIf.vue'
import vBind from './components/directives/vBind.vue'
import vPreAndvOnce from './components/directives/vPreAndvOnce.vue'
import vOn from './components/directives/vOn.vue'
import vHTML from './components/directives/vHTML.vue'
import vText from './components/directives/vText.vue'

// metodos e propriedades computadas
import methodsVue from './components/methods-computed-props-and-watchers/methods.vue'
import comments from './components/methods-computed-props-and-watchers/comments.vue'
import computedProperties from './components/methods-computed-props-and-watchers/computedProperties.vue'

export default {
  name: 'App',
  components: {
    vFor,
    vModel,
    vIf,
    vBind,
    vPreAndvOnce,
    vOn,
    vHTML,
    vText,
    methodsVue,
    comments,
    computedProperties
  }
}
</script>

<style scoped>
  .container {
    padding: 1rem;
    list-style-position: inside;
  }
</style>
