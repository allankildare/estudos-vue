<template>
  <h3>Altere o texto dentro de tapioca</h3>
  <input type="text" v-model="tapioca" />

  <p v-once>Renderizando com v-once: "{{ tapioca }}"</p>
  <span v-pre>Vamos observar como renderiza o v-pre: {{ tapioca }}</span>
  <p>Agora usando a tag HTML pre</p>
  <pre>{{ $data }}</pre>
</template>

<script>
export default {
  name: 'vPreAndvOnce',
  data() {
    return {
      tapioca: 'é muito boa com um queijinho',
    }
  },
}
</script>