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
</script>

<template>
    <div>        
        <h3 class="text-center mb-5">Registro de Clientes</h3>
        <table class="table table-striped table-bordered">
    <thead>
        <th>ID</th>
        <th>Mascota</th>
        <th>Dueño</th>
        <th>Telefono</th>
        <th>Direccion</th>
    </thead>
    <tbody>
                <tr v-for="item in list" :value="item.id">
                    <td>{{item.id}}</td>
                    <td>{{item.name}}</td>
                    <td>{{item.owner}}</td>
                    <td>{{item.phone}}</td>
                    <td>{{item.address}}</td>
                </tr>
            </tbody>
        </table>
</div>
</template>