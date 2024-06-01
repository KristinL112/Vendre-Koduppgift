<!--import av paket och komponenter, funktioner, vue methods -->
<script setup>
  import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav class="navbar navbar-expand-lg">
      <!--Nav links-->
      <div class="container-fluid">
        <RouterLink class="nav-link" to="/">
          <div id="wrapper-logo">
            <img
              src="../assets/img/vendre-optimizers_logo-black.webp"
              alt="logo"
            />
          </div>
        </RouterLink>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <!-- Offcanvas-meny som visas vid knapptryckning -->
        <div
          class="offcanvas offcanvas-end"
          tabindex="-1"
          id="navbarNav"
          aria-labelledby="navbarOffcanvasLgLabel"
        >
          <div class="offcanvas-header">
            <h5 class="offcanvas-title" id="navbarOffcanvasLgLabel">Vendre</h5>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="offcanvas"
              aria-label="Close"
            ></button>
          </div>
          <div class="offcanvas-body">
            <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
              <li class="nav-item">
                <RouterLink class="nav-link" to="/">Home</RouterLink>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </header>
  <!-- RouterView för att visa komponenten -->
  <RouterView />
</template>

<style scoped>
  header {
    line-height: 1.5;
    max-height: 100vh;
  }

  #wrapper-logo {
    position: absolute;
    top: 25%;
    left: 45%;
    transform: translateX(-50%);
  }

  .navbar {
    background-color: rgb(190, 212, 212);
    height: 14vh;
  }

  .nav-item:hover {
    background-color: azure;
  }
  img {
    margin-left: 25%;
  }

  @media (max-width: 768px) {
    #wrapper-logo {
      width: 120px; /* Justera storleken efter behov */
      top: 10%;
      left: 35%;
    }
  }
</style>
