<script setup>
import { ref } from 'vue'
const PersonData = ref ([
    {
        picture: require('../assets/home.png'),
        fullname: 'Joko Keladi',
        address: 'Jl. Meteor VI No. 198',
        hobi: [
            {image: require('../assets/futsal.jpg')},
            {image: require('../assets/catur.jpg')}]
    },
    {
        picture: require('../assets/water.png'),
        fullname: 'Alex Silalahi',
        address: 'Jl. Pandan X No. 30',
        hobi: [
            {image: require('../assets/renang.jpg')}, 
            {image: require('../assets/tinju.jpg')}, 
            {image: require('../assets/sepak bola.jpg')}]
    },
    {
        picture: require('../assets/star.png'),
        fullname: 'Subir Kompani',
        address: 'Jl. Sekar Buana V No. 11',
        hobi: [
            {image: require('../assets/bulu_tangkis.jpg')}, 
            {image: require('../assets/futsal.jpg')}, 
            {image: require('../assets/catur.jpg')}]
    }
 ])

</script>

<template>
    <div class="user-container">
        <div v-for="(person, index) in PersonData" :key="index" class="profile-card">
            <div class="user-info">
                <div class="picture-profile">
                    <img :src="person.picture" alt="profile" class="picture">
                </div>
                <div class="profile-container">
                    <p>fullname: {{ person.fullname }}</p>
                    <p>Address: {{ person.address }}</p>
                </div>
            </div>
            <div class="hobby">
                <p class="user-hobbies">hobbies:</p>
                <div class="list-hobbies">
                    <img v-for="hobbies in person.hobi" :key="hobbies.image" :src="hobbies.image" alt="hobbies">
                </div>
            </div>
        </div>
    </div>
</template>


<style scoped>
    .user-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    gap: 20px;
    }

    .profile-card {
    width: 450px;
    background-color: #fff8e3;
    border: 1px solid #c6c6c6;
    border-radius: 8px;
    padding: 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .user-info {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
    }

    .picture-profile {
    width: 100px;
    height: 100px;
    overflow: hidden;
    border-radius: 50%;
    }

    .picture {
    width: 100%;
    height: 100%;
    object-fit: cover;
    }

    .profile-container {
    margin-left: 20px;
    }

    .profile-container p {
    margin: 5px 0;
    }

    .hobby {
    margin-top: 10px;
    }

    .user-hobbies {
    font-weight: bold;
    margin-bottom: 5px;
    }

    .list-hobbies {
    display: flex;
    gap: 5px;
    }

    .list-hobbies img {
    width: 50px;
    height: 50px;
    object-fit: cover;
    border-radius: 50%;
    }
</style>