<template>
  <div class="study-item">
    <label for="">Qual o seu nome?</label>
    <input type="text" v-model.lazy="userData" />
    <h2 v-if="userData">Valor inicial: {{ userData }}</h2>
    <h2 v-if="userData">Valor computado: {{ greeting }}</h2>
    <p>Explicação:</p>
    <ul>
      <li>Um valor computado só muda quando uma dependência é alterada</li>
      <li>Armazenado em cache</li>
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
  name: 'computedProperties',
  data() {
    return {
      userData: '',
    }
  },
  computed: {
    greeting() {
      return `Você é um monstro ${this.userData}`
    },
  },
}
</script>
