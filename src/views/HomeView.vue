



<script setup>
// Importera profilbild från assets-mappen
import profileImage from '@/assets/Profilbild.png'

//programmerings kunskaper med deras egenskaper
const technologies = [
  {
    name: "C# & .NET",
    icon: "fas fa-code text-purple-600",
    
    
  },
  {
    name: "JavaScript",
    icon: "fab fa-js-square text-yellow-400",
   
  },
  {
    name: "Vue.js",
    icon: "fab fa-vuejs text-green-400",
    
  },
  {
    name: "SQL",
    icon: "fas fa-database text-red-400",
    
  },
  {
    name: "ASP.NET Core Web API",
    icon: "fab fa-html5 text-orange-500",
    
  },
  {
    name: "ASP.NET Core Web app (MVC)",
    icon: "fas fa-layer-group text-blue-500",
    
  }

]
</script>

<template>
  <section class="page-container">
   
    <!-- Profilsektion -->
    <div class="profil-sektion">
      <img
        :src="profileImage"
        alt="Yasin El Kawwash"
        class="profil-bild"
      />

      <div class="intro-text">
        <h1 class="rubrik">
          Hej, jag är <span class="gradient-text">Yasin El Kawwash</span>
        </h1>

        <div class="Yrkesroll">
          Fullstack Developer | 30 år
        </div>

        <p class="Beskrivning">
          Jag bygger moderna frontend- och backendlösningar med passion för kod, design och användarupplevelse.
        </p>
      </div>
    </div>

    <!-- Om mig sektion -->
    <div class="about-sektion">
      <h3 class="sektion-titel">Lite om mig</h3>
      <p class="about-text">
        Utöver mitt tekniska intresse värdesätter jag balans i livet. På fritiden umgås jag gärna 
        med vänner och familj, underhåller en aktiv livsstil genom träning och återhämtar mig 
        med fiske för att upprätthålla kreativitet och fokus.
      </p>
    </div>

    <!-- Teknologisektion -->
    <div class="teknologisektion">
      <h3 class="skills-titel">TEKNISKA KOMPETENSER</h3>
      
      <div class="tech-grid">
        <div 
          v-for="tech in technologies" 
          :key="tech.name"
          class="tech-card"
          :class="tech.borderColor"
        >
          <div class="tech-content">
            <i :class="tech.icon" class="tech-icon"></i>
            <span class="tech-name">{{ tech.name }}</span>
          </div>
        </div>
      </div>
    </div>
    
    <!-- CTA-knapp -->
    <div class="cta-section">
      <router-link 
        to="/projects" 
        class="cta-button"
      >
        <i class="fas fa-rocket button-icon"></i>
        <span class="button-text">Se Mina Projekt</span>
        <i class="fas fa-arrow-right button-arrow"></i>
      </router-link>
    </div>
   
    
    <footer class="site-footer">
      &copy; 2025 Yasin El Kawwash. Alla rättigheter förbehållna.
    </footer>
  </section>
</template>

<style scoped>
/* Huvudlayout */
.page-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 2rem 1rem;
  background-color: #3b4c74;
  color: whitesmoke;
  text-align: center;
  border-radius: 0.5rem;
}

/* Profilsektion */
.profil-sektion {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 3rem;
}

/* Profilbild */
.profil-bild {
  width: 16rem;
  height: 16rem;
  border-radius: 50%;
  border: 4px solid rgba(255, 255, 255, 0.2);
  box-shadow: 0 25px 50px #3b4c74;
  object-fit: cover;
  margin-bottom: 2rem;
}

/* Huvudrubrik */
.rubrik {
  color: whitesmoke;
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 1rem;
  line-height: 1.2;
}

/* Gradient-text effekt */
.gradient-text {
  background: linear-gradient(to right, #9099e8, #a855f7);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.role-tag {
  display: inline-block;
  font-weight: bold;
  font-size: 1.2rem;
  color: whitesmoke;
  background-color: rgba(48, 102, 190, 0.714);
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  margin-bottom: 1rem;
}

/* Beskrivningstext */
.description {
  background-color: rgba(192, 192, 192, 0.3);
  padding: 1rem;
  border-radius: 0.5rem;
  line-height: 1.6;
}

/* Om mig sektionen */
.about-sektion {
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 1rem;
  padding: 1.5rem 2rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  max-width: 42rem;
  margin: 0 auto 2.5rem;
}

/* Om mig sektionens titel */
.sektion-titel {
  font-size: 1.25rem;
  font-weight: 600;
  color: whitesmoke;
  margin-bottom: 1rem;
}

.about-text {
  background-color: rgba(192, 192, 192, 0.3);
  padding: 1rem;
  border-radius: 0.5rem;
  line-height: 1.6;
}

.Teknologisektion {
  margin-bottom: 3rem;
  max-width: 64rem;
  width: 100%;
}

/* Teknologisektionens titel */
.skills-titel {
  color: rgba(192, 192, 192, 0.8);
  max-width: fit-content;
  margin: 0 auto 1.5rem;
  padding: 0.5rem 1rem;
  border-radius: 0.375rem;
  font-size: 1.125rem;
  font-weight: 600;
}

.tech-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
  margin: 0 auto;
}

@media (min-width: 768px) {
  .tech-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

.tech-card {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem;
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 0.75rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

.tech-card:hover {
  transform: scale(1.05);
}

.tech-content {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.tech-name {
  font-weight: 500;
  font-size: 1.125rem;
  color: white;
}

/* CTA-knapp */
.cta-section {
  margin-bottom: 4rem;
}

.cta-button {
  display: inline-flex;
  align-items: center;
  padding: 0.5rem 1.5rem;
  background: linear-gradient(to right, #2563eb, #7c3aed);
  border-radius: 0.75rem;
  font-weight: 600;
  font-size: 1.125rem;
  transition: all 0.3s ease;
  box-shadow: 0 25px 40px rgba(0, 0, 0, 0.5);
  text-decoration: none;
  color: white;
}

.cta-button:hover {
  background: linear-gradient(to right, #1d4ed8, #6d28d9);
  box-shadow: 0 35px 60px rgba(0, 0, 0, 0.6);
  transform: translateY(-0.25rem);
}

/* Footer */
.site-footer {
  position: fixed;
  left: 50%;
  bottom: 1.25rem;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  font-size: 0.8rem;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  transition: all 0.3s ease;
  z-index: 100;
  border: 1px solid rgba(255, 255, 255, 0.2);
  width: auto;
  min-width: 18.75rem;
  text-align: center;
  white-space: nowrap;
}

.site-footer:hover {
  transform: translateX(-50%) translateY(-0.125rem);
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.2);
}

/* Responsiv design */
@media (max-width: 768px) {
  .page-container {
    padding: 1rem 0.5rem;
  }
  
  .rubrik {
    font-size: 2.25rem;
  }
  
  .profil-bild {
    width: 12rem;
    height: 12rem;
  }
  
  .about-sektion {
    padding: 1rem 1.5rem;
  }
  
  .cta-button {
    padding: 0.75rem 1.5rem;
  }
  
  .site-footer {
    bottom: 0.625rem;
    font-size: 0.75rem;
    padding: 0.375rem 0.75rem;
    min-width: 15.625rem;
    width: 90%;
    max-width: 18.75rem;
  }
}

@media (max-width: 480px) {
  .rubrik {
    font-size: 1.875rem;
  }
  
  .role-tag {
    font-size: 1rem;
  }
}

p:hover, a:hover {
  background-color: gray;
}
</style>