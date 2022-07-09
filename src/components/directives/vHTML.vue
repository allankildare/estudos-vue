<template>
  <p v-html="github"></p>
</template>

<script>
export default {
    name: 'vHTML',
    data() {
        return {
            github: 'Acesse meu GitHub <a href="https://github.com/allankildare" target="_blank">Allan Kildare</a>'
        }
    }
}
</script>

<style>

</style>