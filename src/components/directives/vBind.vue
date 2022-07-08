<template>
  <p>Para deixar o botão verdinho você deve digitar "Eu amo Vue"</p>
  <span>Se é verdade ou não, veremos depois ;)</span>
  <br />
  <input type="text" id="loveVue" v-model="loveVue" />
  <button :class="[loveVue === 'Eu amo Vue' ? 'green' : '']">
    {{
      loveVue === 'Eu amo Vue'
        ? 'Que satisfatório né?'
        : 'Deixe-me verde pufavô 🥺'
    }}
  </button>
</template>

<script>
export default {
  name: 'vBind',
  data() {
    return {
      loveVue: '',
    }
  },
}
</script>

<style scoped>
button {
  background-color: #ccc;
}
.green {
  background-color: #1b9608;
}
</style>