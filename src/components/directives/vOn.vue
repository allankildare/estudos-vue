<template>
  <div class="study-item">
    <!-- use v-on ou simplesmente @ -->
    <button v-on:click="counter > 0 ? (counter -= 1) : 0">-</button>
    <span>Quantidade: {{ counter }}</span>
    <button @click="counter += 1">+</button>
    <!-- multiple bindings -->
    <!-- <div v-on="
        mousedown: facaIsso,
        mouseup: facaAquilo
    ">Clique</div> -->
  </div>
</template>

<script>
export default {
  name: 'vOn',
  data() {
    return {
      counter: 0
    }
  },
}
</script>
