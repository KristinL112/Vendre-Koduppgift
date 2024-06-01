<template>
  <div class="card-footer text-body-secondary">
    <div>
      <RouterLink class="footer-link" to="/">Home</RouterLink>
    </div>
    <div class="footer-link">© 2024 Copyright: Kristin Lindén</div>
  </div>
</template>

<style scoped>
  .footer {
    height: 7vh;
  }
  .card-text {
    padding-top: 2vh;
  }

  .card-footer {
    width: 100%; /* För att ta upp hela bredden av sidan */
    background-color: rgb(190, 212, 212);
    padding: 5vh;
    margin-top: 4vh;
    text-align: center; /* Centrera innehållet */
  }

  .footer-link {
    display: flex;
    justify-content: center;
    text-decoration: none;
    color: #000000;
    list-style: none;
  }

  @media (max-width: 768px) {
    .card-footer {
      position: relative;
      height: 25vh;
      margin-top: 7vh;
    }
  }
</style>
