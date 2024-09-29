<template>
  <div>
    <header>
      <nav>
        <ul>
          <li><NuxtLink to="/">Inicio</NuxtLink></li>
          <li><NuxtLink to="/experiencias">Experiencias</NuxtLink></li>
          <li><NuxtLink to="/about">Acerca de</NuxtLink></li>
        </ul>
      </nav>
    </header>

    <main>
      <NuxtPage />
    </main>

    <footer>
      <p>Uso de layouts en Nuxt.js</p>
    </footer>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body {
  font-family: 'Roboto'; 
  background-color: #F5F7FA; 
  margin: 0;
}

header {
  background-color: #1A73E8; 
  color: white;
  padding: 15px; 
}

nav ul {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
}

nav ul li {
  margin-right: 20px;
}

nav a {
  color: white; 
  text-decoration: none; 
  transition: color 0.3s; 
  padding: 10px 15px; 
  border-radius: 5px; 
  font-size: 25px;
}

nav a:hover {
  background-color: #B3C7E6; 
  color: #1A73E8; 
}

main {
  padding: 20px; 
  min-height: calc(100vh - 120px); 
}

footer {
  background-color: #1A73E8; 
  color: white;
  text-align: center; 
  padding: 10px;
  position: fixed;
  width: 100%;
  bottom: 0; 
  font-size: 18px;
}
</style>
