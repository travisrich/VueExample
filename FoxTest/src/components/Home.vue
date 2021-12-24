<template>
    <div class="home" :v-if="profiles">
        <p>The number of employee profiles are: <span class="profileCount"> {{ profiles.length }} </span></p>
        <div class="profileWrap" :v-for="profile in profiles">
            <div v-for="item in profiles" :key="item.id">
                <Profile :profileData={item} :v-for="item in profiles" />
            </div>
        </div>
    </div>
</template>

<script>
    import Profile from './Profile.vue';

    export default {
        name: 'home',
        components: {
            Profile
        },
        props: {
            index: Number,
            profile: Object,
            item: Object,
            jsonData: Object
        },
        data() {
            return {
                profiles: [],
                i: 0,

            }  
        },
        methods: {
            getProfiles() {
                for (this.i = 0; this.i < this.jsonData.info.length; this.i++) {
                    this.profiles.push(this.jsonData.info[this.i]);
                }
            }
        },
        mounted() {
            this.getProfiles();
        }
    };
</script>

<style scoped>
    .profileWrap {
        border: 1px solid;
        max-width:800px;
        margin:0px auto;
    }
    .profileCount {
        font-weight: bold;
    }
    ul {
        padding:0px;
    }
    li {
        list-style: none;
    }
</style>

