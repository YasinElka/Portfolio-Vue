
<template>
  <div class="container">
    <!-- Titel för certifikaten -->
    <h2>Certifikat:</h2>

    <!-- Lista över certifikat -->
    <ul>
      <!-- Loopar genom certifikatlistan och visar varje certifikat som en klickbar länk -->
      <li v-for="cert in certifikatLista" :key="cert.id">
        <a href="#" @click.prevent="visaCertifikat(cert.bild)">
          📄 {{ cert.namn }}
        </a>
      </li>
    </ul>

    <!-- Modal-fönster som visas när ett certifikat klickas -->
    <div v-if="certifikatBild" class="modal-overlay" @click.self="certifikatBild = null">
      <div class="modal-content">
        <img :src="certifikatBild" class="stor-certifikat" alt="Certifikat" />
        <button @click="certifikatBild = null">Stäng</button>
      </div>
    </div>
  </div>
</template>

<script>
// Importerar certifikatbilden
import certifikatBild from '@/assets/certifikat-Yasin-elkawwash-grundlaggande-programmering.png';
import certifikatBild1 from '@/assets/certifikat-Yasin-elkawwash-programmering-fordjupning.png';
import certifikatBild2 from '@/assets/Certifikat-nckl8-Yasin-El-kawwash-programmering-c-fullstack.png';
export default { 
  name: 'CertificationsView',
  data() {
    return {
      certifikatBild: null,
      certifikatLista: [
        {
          id: 1,
          namn: 'Grundläggande programmering',
          bild: certifikatBild  // Använd den importerade variabeln
        },
        {
          id: 2,
          namn: 'Fördjupning programmering',
          bild: certifikatBild1  // Använd den importerade variabeln
        },
        {
          id: 3,
          namn: 'Programmering C# Fullstack',
          bild: certifikatBild2  // Använd den importerade variabeln
        }
      ]
    };
  },
  methods: {
    visaCertifikat(bild) {
      this.certifikatBild = bild;
    }
  }
};
</script>

<style>
/* Behållare för hela sidan */
body {
  font-family: 'Segoe UI', sans-serif;
  padding: 2rem;
  max-width: 1000px;
  margin: auto;
  background-color:#3b4c74;
  border-radius: 10px;
}


/* Rubriken */
h2 {
  text-align: center;
  margin-bottom: 1.5rem;
}

/* Lista utan punkter */
ul {
  list-style: none;
  padding: 0;
}

/* Mellanrum mellan certifikat-länkarna */
li {
  margin-bottom: 1rem;
}

/* Stil för klickbar länk */
a {
  color: #42b983;
  font-weight: bold;
  text-decoration: none;
  cursor: pointer;
  align-items: center;
}

a:hover {
  text-decoration: underline;
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
  background:whitesmoke;
  padding: 40px;
  border-radius: 8px;
  text-align: center;
}

/* Bild i modalen */
.stor-certifikat {
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
}

button:hover {
  background: #36906d;
}


</style>
