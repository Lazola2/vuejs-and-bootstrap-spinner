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
                   name: 'Trevor Noah',
                   picture: 'https://i.postimg.cc/MKcHVZnK/Trevor-noah.jpg',
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

<style scoped>
    .profile-card {
        background: #fff;
        border-radius: 15px;
        box-shadow: 0 0 15px 0 gray;
        margin: 10px;
        padding: 10px;
        display: flex;
        align-items: center;
    }

    .profile-info {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding-left: 2rem;
        justify-content: center;
        gap: 0;
    }
    .profile-image img {
        height: 60px;
        width: 60px;
        object-fit: cover;
        border-radius: 50%;
        border: 4px solid rgb(26, 193, 87);
        padding: 2px;
    }
</style>