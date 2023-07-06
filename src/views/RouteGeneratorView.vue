<script setup>
import RouteGenerator from '../components/RouteGenerator.vue'
import clients from '../json/clients.json'

</script>

<template>
  <main>
    <RouteGenerator :clients="clients" />
  </main>
</template>
