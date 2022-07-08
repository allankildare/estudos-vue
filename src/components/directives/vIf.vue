<template>
    <h1>Você gosta de café?</h1>
    <input v-model="coffee" value="sim" type="radio" id="sim" />
    <label for="sim">Simm!!</label>

    <input v-model="coffee" value="nao" type="radio" id="nao" />
    <label for="nao">Não</label>

    <p v-if="coffee === 'sim'">Boaa, é muuito bom né?</p>
    <p v-else-if="coffee === 'nao'">Como você consegue?? 😩</p>
</template>

<script>

export default {
    name: 'vIf',
    data() {
        return {
            coffee: ''
        }
    }
}
</script>
