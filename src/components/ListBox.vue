<script setup>
import { ref } from 'vue'
const item = ref('')
defineProps({
  title: {
    type: String,
    required: true
  },

  list: {
    type: Array,
    required: true
  }
})
</script>

<template>
        <div class="row">
            <h5 class="mt-2 mb-2">{{ title }}</h5>
            <div class="col-md-12">
                <select id="disponibles" class="form-select" multiple aria-label="multiple select example" v-model="item">
                    <option v-for="item in list" :value="item.id">{{ item.name }}</option>
                </select>
            </div>
            <span>Seleccionado: {{ item }}</span>
        </div>
</template>