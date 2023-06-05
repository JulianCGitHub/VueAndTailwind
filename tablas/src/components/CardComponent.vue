<script setup>
const borrarTarjeta = (index) =>{
    console.log('Borrar tarjeta',index)
    emit('borrarTarjeta',index)
}

const emit = defineEmits(['borrarTarjeta'])

const props = defineProps(
    {
        name:{
            type:String,
            default: 'No name'
        },
        mail:{
            type:String,
            default: 'No email'
        },
        index:{
            type:Number,
        }
    }
)
</script>
<template>
    <div class="w-60 rounded shadow overflow-hidden">
        <div class="inline-block align-top">
            <img src="https://picsum.photos/40" alt="">
        </div>
        <div class="inline-block pl-2">
            <h2 class="text-md font-semibold">{{ props.name}}</h2>
            <p class="text-xs">{{ props.mail }}</p>
        </div>
        <span class="inline-block ml-4 bg-red-400 text-white rounded leading-0 py-0 px-2 hover:cursor-pointer hover:bg-red-600" @click="borrarTarjeta (props.index) ">
             X 
        </span>
    </div>
</template>