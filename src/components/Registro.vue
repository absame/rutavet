
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
    <thead>
        <th>ID</th>
        <th>Mascota</th>
        <th>Dueno</th>
        <th>Telefono</th>
        <th>Direccion</th>
    </thead>
    <tbody>
        <tr></tr>
    </tbody>
</div>
</template>