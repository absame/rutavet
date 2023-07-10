<script setup>
import { RouterLink, RouterView } from 'vue-router'
import RouteGenerator from './components/RouteGenerator.vue'
import Registro from './components/Registro.vue'
</script>

<template>
  <header>
    <img alt="deydol logo" class="logo" src="img/deydol.jpg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="RutaVET" />

      <nav>
        <RouterLink to="/">Inicio</RouterLink>
        <RouterLink to="/routegenerator">Generador de rutas</RouterLink><br>
        <RouterLink to="/registro">Registro de Clientes</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
  height: 200px;
  width: 200px;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
