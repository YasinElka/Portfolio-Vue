<template>
  <div class="container">
    <!-- Titel för projekten -->
    <h2>Mina Projekt</h2>

    <!-- Lista över projekt -->
    <ul>
      <!-- Loopar genom projektlistan och visar varje projekt som en klickbar länk -->
      <li v-for="project in projects" :key="project.id">
        <a href="#" @click.prevent="visaProjektBild(project.bild)">
          📸 {{ project.namn }}
        </a>
      </li>
    </ul>

    <!-- Modal-fönster som visas när ett projekt klickas -->
    <div v-if="projektBild" class="modal-overlay" @click.self="projektBild = null">
      <div class="modal-content">
        <img :src="projektBild" class="stor-projekt-bild" alt="Projektbild" />
        <button @click="projektBild = null">Stäng</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectsView',
  data() {
    return {
      projektBild: null,
      projects: [
        {
          id: 1,
          namn: 'Webbapp för tidrapportering för anställda byggd på ett MVC-ramverk',
          bild: require('@/assets/EmployeeMVC.png'),
        },
        {
          id: 2,
          namn: 'En view av registrering av anställda/(Mvc-ramverk)',
          bild: require('@/assets/EmployeeMVC1.png'),
        },
        {
          id: 3,
          namn: 'En view av ett kontakt formulär.(Mvc-ramverk)',
          bild: require('@/assets/EmployeeMVC2.png'),
        },
        {
          id: 4,
          namn: 'Kod från ett konsol program (C#)',
          bild: require('@/assets/FizzBuzz.png'),
        },
        {
          id: 5,
          namn: 'Resultatet från ett konsol program(C#)',
          bild: require('@/assets/FizzBuzz1.png'),
        },
        {
          id: 6,
          namn: 'Kod från mitt TicTacToe spel(C#)',
          bild: require('@/assets/TicTacToe.png'),
        },
        {
          id: 7,
          namn: 'TicTacToe spel(C#)',
          bild: require('@/assets/TicTacToe1.png'),
        },
        {
          id: 8,
          namn: 'ASP.NET CORE WEB API(C#)',
          bild: require('@/assets/BooksAPI-Kod.png'),
        },
        {
          id: 9,
          namn: 'ASP.NET CORE WEB API(C#)',
          bild: require('@/assets/BooksAPI.png'),
        },
        {
          id: 10,
          namn: 'ASP.NET CORE WEB API(C#)',
          bild: require('@/assets/BooksAPI1.png'),
        },
        {
          id: 11,
          namn: 'Bookapplication(C#/MVC)',
          bild: require('@/assets/BookApp.png'),
        },
        {
          id: 12,
          namn: 'BookApplication(C#/MVC)',
          bild: require('@/assets/BookApp1.png'),
        },
        {
          id: 13,
          namn: 'Bookapplication(C#/MVC)',
          bild: require('@/assets/BookApp2.png'),  
        },
        {
          id: 14,
          namn: 'Bookapplication(C#/MVC)',
          bild: require('@/assets/BookApp3.png'),
        },
        {
          id: 15,
          namn: 'VUE-project(Vue.js/JavaScript)',
          bild: require('@/assets/VUE-PORTFOLIO.png'),
        },
        {
          id: 16,
          namn: 'VUE-project(Vue.js/JavaScript)',
          bild: require('@/assets/VUE-PORTFOLIO.2.png'),
        },
        {
          id: 17,
          namn: 'VUE-project(Vue.js/JavaScript)',
          bild: require('@/assets/VUE-PORTFOLIO.3.png'),
        },
        {
          id: 18,
          namn: 'VUE-project(Vue.js/JavaScript)',
          bild: require('@/assets/VUE-PORTFOLIO.4.png'),
        },
        {
          id: 19,
          namn: 'VUE-project(Vue.js/JavaScript)',
          bild: require('@/assets/APP-VUE.png'),
        },
      ],
    };
  },
  methods: {
    visaProjektBild(bild) {
      this.projektBild = bild;
    }
  }
};
</script>

<style scoped>
/* Behållare för hela sidan */
.container {
  font-family: 'Segoe UI', sans-serif;
  padding: 2rem;
  max-width: 1000px;
  margin: auto;
  margin-top: 10px;
  background-color: #3b4c74;
  border-radius: 10px;
  color: white;
  min-height: 100vh;
}

/* Rubriken */
h2 {
  text-align: center;
  margin-bottom: 1.5rem;
  color: white;
}

/* Lista utan punkter */
ul {
  list-style: none;
  padding: 0;
}

/* Mellanrum mellan projekt-länkarna */
li {
  margin-bottom: 1rem;
  background-color: #3b4c74;
  border-radius: 0.5rem;
  padding: 0.5rem;
}

/* Stil för klickbar länk */
a {
  color: #42b983;
  font-weight: bold;
  text-decoration: none;
  cursor: pointer;
  align-items: center;
  display: block;
  padding: 0.5rem;
}

a:hover {
  text-decoration: underline;
  color: #36906d;
}

/* Modal-overlay – gråtonad bakgrund bakom bilden */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 999;
}

/* Själva modal-rutan */
.modal-content {
  background: whitesmoke;
  padding: 40px;
  border-radius: 8px;
  text-align: center;
  max-width: 90vw;
  max-height: 90vh;
}

/* Bild i modalen */
.stor-projekt-bild {
  max-width: 80vw;
  max-height: 80vh;
  border-radius: 8px;
  margin-bottom: 10px;
}

/* Stäng-knapp */
button {
  background: #42b983;
  border: none;
  padding: 10px 20px;
  color: white;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
}

button:hover {
  background: #36906d;
}



</style>