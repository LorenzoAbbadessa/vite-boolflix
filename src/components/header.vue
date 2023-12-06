<script>
import { store } from '../store.js'
export default {
    name: "header",
    data() {
        return {
            store
        }

    },
    methods: {
        confirm() {
            this.$emit("search")

        }

    }

}
</script>

<template>
    <header>
        <input v-model="store.search" @keyup.enter="confirm" type="text" placeholder="Cerca Film...">
    </header>
</template>

<style></style>