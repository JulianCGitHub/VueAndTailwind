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

</script>

<template>
<CardComponent v-for="(user, index) in users" 
:key="index" :name="user.name" :mail="user.mail" :index="index"
 @borrarTarjeta="borrarTarjeta"/>
</template>


<style scoped>

</style>
