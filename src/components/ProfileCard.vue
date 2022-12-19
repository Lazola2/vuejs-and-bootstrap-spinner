<template>
    <div class="profile-card">
        <div class="profile-image">
            <img :src="userData.picture" :alt="userData.name">
        </div>
        <div class="profile-info">
            <span>Written By</span>
            <h3>{{userData.name}}</h3>
            <p v-text="userData.bio"></p>
        </div>
    </div>
</template>

<script>
    import {ref} from 'vue'
    const loadUserData = async () => {
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve({
                   name: 'Lazola Makubalo',
                   picture: '<link>',
                   bio: 'A web and a software developer'
                })
            }, 1000)
        })
    }

    export default {
        name: 'ProfileCard',
        async setup() {
            const userData = ref(await loadUserData());
            return {userData}
        }
    }
</script>

<style>

</style>