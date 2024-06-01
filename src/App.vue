<template>
  <!--en class "app" och en class som binder till mode är dark eller light  -->
  <div class="app">
    <header>
      <!-- Nav -->
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
