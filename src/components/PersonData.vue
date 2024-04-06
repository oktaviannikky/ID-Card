<script setup>
import { ref } from 'vue'
const PersonData = ref ([
    {
        picture: './assets/home.png',
        fullname: 'Joko Keladi',
        address: 'Jl. Meteor VI No. 198',
        hobi: [
            {image: './assets/futsal.jpg'},
            {image: './assets/catur.jpg'}]
    },
    {
        picture: './assets/water.png',
        fullname: 'Alex Silalahi',
        address: 'Jl. Pandan X No. 30',
        hobi: [
            {image: './assets/renang.jpg'}, 
            {image: './assets/tinju.jpg'}, 
            {image: './assets/sepak bola.jpg'}]
    },
    {
        picture: './assets/star.png',
        fullname: 'Subir Kompani',
        address: 'Jl. Sekar Buana V No. 11',
        hobi: [
            {image: './assets/bulu_tangkis.jpg'}, 
            {image: './assets/futsal.jpg'}, 
            {image: './assets/catur.jpg'}]
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
                    <img v-for="hobbies in person.hobi" :key="hobbies" :src="hobi" alt="hobbies">
                </div>
            </div>
        </div>
    </div>
</template>


<style>

</style>