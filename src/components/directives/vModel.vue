<template>
  <div class="study-item">
    <h3>Digite aqui:</h3>
    <input type="text" v-model="message">
    <br>
    <h4>Veja a mágica acontecer e seu texto aparecer abaixo:</h4>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
    name: 'vModel',
    data() {
        return {
            message: ''
        }
    }
}
</script>

<style>

</style>