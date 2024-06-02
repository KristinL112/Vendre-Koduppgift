<template>
  <main>
    <div id="wrapper-contact">
      <h2 class="header">Vi jobbar på Vendre</h2>
      <div class="images">
        <div v-for="user in users" :key="user.id">
          <img class="user-img" :src="user.avatar" alt="user avatar" />
          <div class="user-info">
            {{ user.first_name }} {{ user.last_name }}
            <span @click="toggleEmail(user.id)" style="cursor: pointer">
              <div>
                <img
                  class="email-icon"
                  src="../assets/img/envelope-fill.svg"
                  alt="email icon"
                /></div
            ></span>
            <p class="email-info" v-if="showEmail[user.id]">
              <a :href="'mailto:' + user.email">{{ user.email }}</a>
            </p>
          </div>
        </div>
      </div>
      <!-- Framåt knapp -->
      <div>
        <router-link class="btn btn-primary" to="/about">Framåt</router-link>
      </div>
    </div>
  </main>
</template>

<script>
  import axios from 'axios'

  export default {
    data() {
      return {
        users: [],
        showEmail: {} // För att spåra om e-mail visas för varje användare
      }
    },
    mounted() {
      axios
        .get('https://reqres.in/api/users')
        .then(response => {
          this.users = response.data.data
          this.users.forEach(user => {
            this.$set(this.showEmail, user.id, false) // Initiera showEmail-objekt för varje användare
          })
        })
        .catch(error => {
          console.log(error)
        })
    },
    methods: {
      toggleEmail(userId) {
        this.showEmail[userId] = !this.showEmail[userId] //Toggle visar email-värdet
      }
    }
  }
</script>

<style scoped>
  .header {
    margin-top: 1vh;
    margin-bottom: 4vh;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding-top: 10px;
    font-weight: 500;
  }
  h2.header {
    font-size: 2rem;
    font-weight: 500;
  }

  .images {
    margin-top: 2vh;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .images div {
    flex-basis: calc(33.33% - 20px);
    margin: 10px;
  }

  .user-img {
    border-radius: 50%;
    width: 250px;
    height: auto;
    margin-left: 25%;
  }

  .user-info {
    text-align: center;
    height: 10vh;
    font-weight: 500;
    font-size: 1.2rem;
  }

  img.email-icon {
    width: 30px; /* Bredd för email-ikonen */
    height: auto; /* Justera höjden automatiskt för att behålla proportionerna */
  }

  a {
    color: #121212;
  }

  .btn {
    float: right;
    transition: background-color 0.3s ease;
    background-color: rgb(190, 212, 212);
    border-color: rgb(190, 212, 212);
    color: #3e3d3d;
    margin-right: 10px;
    border-radius: 1px;
  }

  .btn:hover,
  button:active {
    background-color: rgb(120, 134, 134);
  }

  @media (max-width: 768px) {
    img {
      width: 16px;
    }
    .user-img {
      border-radius: 50%;
      width: 250px; /* Bredd bilderna */
      height: auto;
      margin: 5%;
    }
  }
</style>
