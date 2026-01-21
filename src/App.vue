<template>
  <div>
    <nav class="navbar">
      <router-link to="/">Hem</router-link>
      <router-link to="/projects">Projekt</router-link>
      <router-link to="/certifications">Certifikat</router-link>
      <router-link to="/Contact">Kontakt</router-link>
    <a href="https://www.linkedin.com/in/yasin-e-a44828a8" target="_blank" class="w3-bar-item w3-button w3-padding-large w3-right">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn" style="height:30px;"></a>
    
    <a href="https://github.com/YasinElka/Portfolio" target="_blank" class="w3-bar-item w3-button w3-padding-large w3-right">
    <img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="GitHub" style="height:30px;"></a>
    
    </nav>

    
 <router-view />
  </div>
</template>

<style scoped>
.navbar {
  background: hsl(210, 4%, 36%);
  padding: 20px;
  margin: auto;
  
box-shadow: inset 0 -3px 0 rgba(0, 0, 0, 0.2);
border-radius: 5px;
}
.navbar a {
  color: whitesmoke;
  margin-right: 60px;
  text-decoration: none;
  font-weight: bold;
}
.navbar a.router-link-active {
  text-decoration: underline-color whitesmoke;
 
}
.navbar a:hover {
  text-decoration:underline;
  opacity: 0.8;
}

#foooter {
  background: hsl(210, 4%, 36%);
  color: whitesmoke;
  text-align: center;
  padding: 10px;
  position: fixed;
  bottom: 0;
  width: 100%;
}
</style>