<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header class="wrapper bg-teal-800 border border-black h-14">
  <img alt="Vue logo" class="logo" src="@/assets/isclab.png" width="200" height="30" style="margin: 5px;" />

    <div>

      <nav class="navv" style="margin: 5px;">
        <RouterLink to="/"><p class="hover:text-teal-200 text-white">Índice</p></RouterLink>
        <RouterLink to="/about"><p class="hover:text-teal-200 text-white">Formulario</p></RouterLink>
        <RouterLink to="/personas"><p class="hover:text-teal-200 text-white">Ver Registros</p></RouterLink>
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
.navv{
  display: inline-flex;
  font-size: 20px;
  margin-bottom: 20px;
}
.logo {
  display: block;
  margin: 0 auto 2rem;
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
