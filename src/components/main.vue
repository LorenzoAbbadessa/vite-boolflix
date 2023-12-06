<script>
import { store } from '../store.js'
export default {
    name: "main",
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <section>
        <div v-for="name in store.container">
            <h2>{{ name.title }}</h2>
            <h2>{{ name.original_language }}</h2>
            <h2>{{ name.vote_average }}</h2>
        </div>
    </section>
</template>

<style scoped></style>

