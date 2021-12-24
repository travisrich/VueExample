<template>
    <div id="app">
        <h1 class="title">Employee Profiles</h1>
        <Home :jsonData={info} v-if="info" />
    </div>
</template>

<script>
    import Home from './components/Home.vue';
    import axios from 'axios';

    export default {
        name: 'app',
        components: {
            Home
        },
        data() {
            return {
                info: null,
                profiles: null
            }
        },
        async created() {
            try {
                const res = await axios.get('https://api.json-generator.com/templates/JLSjfQ9WVjJE/data?access_token=m054m7gvmvxx6xuufoaysf554e290rhr5qtqy3fk');
                this.info = res.data;
            } catch(e) {
                console.error(e);
            }
        }
    };
</script>

<style>
    #app {
        font-family: Arial;
    }

    .title {
        color: red;
    }
</style>