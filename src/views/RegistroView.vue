<script setup>
import Registro from '../components/Registro.vue'
import clients from '../json/clients.json'

</script>

<template>
  <main>
    <RouteGenerator :clients="clients" />
  </main>
</template>
