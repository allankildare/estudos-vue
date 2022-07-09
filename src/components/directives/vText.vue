<template>
  <input type="text" v-model="tea" />
  <p>Renderizado com v-text</p>
  <p v-text="tea"></p>
  <p>Renderizado com mustache</p>
  <p>{{ tea }}</p>
</template>

<script>
export default {
    name: 'vText',
    data() {
        return {
            tea: 'Eu gosto muito de chá de hibisco'
        }
    }
}
</script>

<style>

</style>