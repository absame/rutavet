
<script setup> 
import ListBox from './ListBox.vue';

defineProps({
  clients: {
    type: Array,
    required: true
  }
})

function addElement(){
    console.log(item)
}

</script>
<template>
    <div>        
        <h3 class="text-center mb-5">Route Generator</h3>
    <div class="row">
            <div class="col-md-5">
                <ListBox title="Clientes disponibles" :list="clients"></ListBox>
            </div>
            <div class="col-md-2">
                <button v-on:click="addElement"> + </button>
                <button> - </button>
            </div>
            <div class="col-md-5">
                <ListBox title="Clientes en Ruta" :list="[]"></ListBox>

            </div>
    </div>
</div>
</template>