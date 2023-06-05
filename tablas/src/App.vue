<script setup>
import {ref} from 'vue';
import CardComponent from '@/components/CardComponent.vue';

const users = ref([
    {
        name: 'Juana de arco',
        mail: 'Juanita@casialgo.com',
    },
    {
        name: 'Rey arturo',
        mail: 'Derrocado@eldiablo.com',
    },
])

const borrarTarjeta = (index) =>{
console.log('KILL to', index)
users.value.splice (index,1)
console.log(users)

}

let name,mail

const addUser = () =>{
    const newUser = {
        name: name,
        mail: mail
    }
    users.value.unshift (newUser)
}

</script>

<template>
    <input type="text" v-model="name" placeholder="Escriba su nombre" class="border rounded">
    <input type="text" v-model="mail" placeholder="Escriba su correo" class="border rounded">
    <button class="bg-green-200 px-2 py-1 rounded mt-2" @click="addUser">Añadir</button>
<CardComponent v-for="(user, index) in users" 
:key="index" :name="user.name" :mail="user.mail" :index="index"
 @borrarTarjeta="borrarTarjeta"/>
</template>


<style scoped>

</style>
