<template>
    <div>
        <h1 v-bind:style="{ textDecoration: decoration }">Hello {{ name }} </h1>
        <input type="text" v-model="name">
        <br>
        <!-- v-bind pode ser resumido a : -->
        <a :href="link">Link para GitHub</a>
    </div>
</template>

<script>
export default {
    data: () => ({
        name: 'Allan',
        link: 'https://github.com/allankildare',
        decoration: 'underline'
    })
}
</script>