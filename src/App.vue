<!--App.vue-->

<template>
  <div class="app">
    <header>
      <NavBar />
      <FooterComponent />
    </header>
  </div>
</template>

<script setup>
  // Importerar Navbar och Footer
  import FooterComponent from './components/FooterComponent.vue'
  import NavBar from './components/NavBar.vue'
</script>
