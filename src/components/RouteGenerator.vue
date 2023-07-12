
<script setup> 
import { ref, reactive } from 'vue' 
import ListBox from './ListBox.vue';  
import clients from '../json/clients.json'

// const props = defineProps({
//   clients: {
//     type: Array,
//     required: true
//   }
// })

let Clients = reactive([...clients]);
let ClientsOnRoute = reactive([]);
const selectedItems1 = reactive([])
const selectedItems2 = reactive([])

function moveToRight() { 
    const data = Clients.filter(el => selectedItems1.includes(el.id))
    ClientsOnRoute = reactive(ClientsOnRoute.concat(data))
    Clients = Clients.filter(item => !data.includes(item)); 
    console.log(Clients, ClientsOnRoute)

}
function moveToLeft() {
    const data = ClientsOnRoute.filter(el => selectedItems2.includes(el.id))
    Clients =reactive( Clients.concat(data) );
    ClientsOnRoute = ClientsOnRoute.filter(item => !data.includes(item));  
    console.log(Clients, ClientsOnRoute)
}

</script>

<template>
    <div>        
        <h3 class="text-center mb-5">Route Generator</h3>
    <div class="row">
            <div class="col-md-5">
                <ListBox title="Clientes disponibles" :list="Clients" v-model="selectedItems1"></ListBox>
            </div>
            <div class="col-md-2">
                <button @click="moveToLeft"> &lt;&lt; </button>
                <button @click="moveToRight"> >> </button>

            </div>
            <div class="col-md-5">
                <ListBox title="Clientes en Ruta" :list="ClientsOnRoute" v-model="selectedItems2"></ListBox>

            </div>
            
            <br><br><button type="button" class="btn btn-primary btn-lg btn-block">Generar Ruta</button>
            
    </div>
</div>
</template>