<template>
  <label>Edite o texto dentro do campo: </label>
  <input type="text" v-model="tea" />
  <p>Renderizado com v-text</p>
  <b><p v-text="tea"></p></b>
  <p>Renderizado com mustache</p>
  <b><p>{{ tea }}</p></b>
</template>

<script>
export default {
  name: 'vText',
  data() {
    return {
      tea: 'Eu gosto muito de chá de hibisco',
    }
  },
}
</script>

<style scoped>
input {
    width: 250px;
}
</style>