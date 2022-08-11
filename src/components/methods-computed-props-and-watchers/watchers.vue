<template>
  <div class="study-item">
    <h1>Watchers</h1>
    <input type="number" v-model="counter" />
    <p><em>Lembre-se de checar o console</em></p>
    <p>Explicação:</p>
    <ul>
      <li>São bons para atualizações assíncronas</li>
      <li>Muito úteis em atualizações/transições com mudança de dados</li>
      <li>Deve ser usado como uma propriedade, no lugar dos dados</li>
      <li>
        Por padrão é apenas um <em>getter</em>, mas também pode ser definido
        como um <em>setter</em>.
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'watchers',
  data() {
    return {
      counter: 0,
    }
  },
  watch: {
    counter(newValue) {
      console.log('O contador mudou para ' + newValue)
    },
  },
}
</script>
