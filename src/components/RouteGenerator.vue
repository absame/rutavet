
<script setup> 
import { ref, reactive } from 'vue'
import ListBox from './ListBox.vue'; 
let elementToSend = ref(0)
const clientsOnRoute = reactive([])
const props = defineProps({
  clients: {
    type: Array,
    required: true
  }
})

function addElement(){ 
    clientsOnRoute.push(props.clients[elementToSend])
}

function changeElement(e){
    elementToSend = e.target.value - 1
}

</script>

<template>
    <div>        
        <h3 class="text-center mb-5">Route Generator</h3>
    <div class="row">
            <div class="col-md-5">
                <ListBox title="Clientes disponibles" :list="clients" @change="changeElement"></ListBox>
            </div>
            <div class="col-md-2">
                <button @click="addElement"> + </button>
                <button> - </button>
            </div>
            <div class="col-md-5">
                <ListBox title="Clientes en Ruta" :list="clientsOnRoute"></ListBox>

            </div>
    </div>
</div>
</template>