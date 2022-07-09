<template>
  <div @mousemove="xCoordinate" :style="{ backgroundColor: `hsl(${x}, 80%, 50%)` }">
  <p>Pixels no eixo X: {{ x }}</p>
  <button @click="decrement">-</button>
  <span>{{ counter }}</span>
  <button @click="increment">+</button>

  </div>
</template>

<script>
export default {
    name: 'methods',
    data() {
        return {
            counter: 0,
            x: ''
        }
    },
    methods: {
        increment() {
            this.counter += 1
        },
        decrement() {
            this.counter -= 1
        },
        xCoordinate(event) {
            this.x = event.clientX
        }
    },
}
</script>

<style>

</style>