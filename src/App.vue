<script>
import axios from 'axios';
import { store } from './store.js'
import centro from './components/main.vue';
import testa from './components/header.vue';
export default {
    components: {
        testa,
        centro,
    },
    data() {
        return {
            store
        }
    },


    methods: {
        getInfoOld() {
            const call = `${store.api_url}?api_key=${store.api_key}&query=${store.search}`;

            axios.get(call).then(res => {
                this.store.container = res.data.results



            })

        },
        getInfo() {


            const options = {
                method: 'GET',
                url: this.store.api_url,
                params: {
                    query: this.store.search,
                    api_key: this.store.api_key
                }
            };

            axios.request(options).then(response => {
                this.store.container = response.data.results
            })
        }
    }
}
</script>


<template>
    <testa @search="getInfo" />
    <centro />
</template>

<style scoped></style>