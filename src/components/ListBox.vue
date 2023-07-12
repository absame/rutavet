<script setup>
import { ref, watch } from 'vue'
//let selectedItems = ref([])
const props = defineProps({
  title: {
    type: String,
    required: true
  },

  list: {
    type: Array,
    required: true
  },
})


const selectedItems = ref([...props.list]);

watch(selectedItems, (newVal) => {
  emit('update:value', newVal);
});

watch(() => props.list, (newVal) => {
  selectedItems.value = [...newVal];
});

const emit = defineEmits(['update:items', 'update:value'])
// @change="emit('update:items', selectedItems)"
</script>

<template>
        <div class="row">
            <h5 class="mt-2 mb-2">{{ title }}</h5>
            <div class="col-md-12">
                <select class="form-select" multiple aria-label="multiple select example" v-model="selectedItems">
                    <option v-for="item in list" :value="item.id">{{ item.name }}</option>
                </select>
            </div>
            <span>Seleccionado: {{ selectedItems }}</span>
        </div>
</template>