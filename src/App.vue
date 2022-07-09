<template>
  <div>
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
  </div>
</template>

<script>
import vFor from './components/directives/vFor.vue'
import vModel from './components/directives/vModel.vue'
import vIf from './components/directives/vIf.vue'
import vBind from './components/directives/vBind.vue'
import vPreAndvOnce from './components/directives/vPreAndvOnce.vue'
import vOn from './components/directives/vOn.vue'
import vHTML from './components/directives/vHTML.vue'
import vText from './components/directives/vText.vue'
import methodsVue from './components/methods-computed-props-and-watchers/methods.vue'
import comments from './components/methods-computed-props-and-watchers/comments.vue'

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
    comments
  }
}
</script>

<style></style>
