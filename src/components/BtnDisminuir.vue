<template>
    <button @click="accionDisminuir(30)">Disminuir</button>
</template>

<script>
import {mapActions} from 'vuex'
export default {
    methods: {
        ...mapActions(['accionDisminuir'])
    }
}
</script>

<style>

</style>
