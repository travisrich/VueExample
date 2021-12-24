<template>
    <div class="profile">
        <p><span class="profileField">Username</span>: {{ this.userName }} </p>
        <p><span class="profileField">Name</span>: {{ this.name }} </p>
        <p><span class="profileField">Email</span>: {{ this.email }} </p>
        <p><span class="profileField">Birthday</span>: {{ this.birthday }} </p>
        <p><span class="profileField">About Me</span>: {{ this.about }} </p>
        <p><span class="profileField">Client</span>: {{ this.client }} </p>

    </div>
</template>

<script>
    export default {
        name: 'profile',
        props: {
            profileData: Object
        },
        data() {
            return {
                userName: this.profileData.item.username,
                name: this.profileData.item.profile.name,
                email: this.profileData.item.email,
                birthday: this.profileData.item.profile.dob,
                about: this.profileData.item.profile.about,
                client: this.profileData.item.profile.company



            }
        }
    };
</script>

<style scoped>
    .profile {
        padding:10px;
    }
    .profileField {
        font-weight: bold;
    }
</style>