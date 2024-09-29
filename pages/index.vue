<template>
  <div class="welcome-container">
    <h1>Bienvenidos</h1>
    <h2>Uso de layouts en Nuxt</h2>
    <p>
      En Nuxt.js, los layouts permiten definir estructuras comunes que se aplican a varias páginas, como encabezados, menús de navegación o pies de página. Esto evita la repetición de código y asegura que el diseño se mantenga coherente en todo el sitio.
      Como en nuestro trabajo, donde usamos un layout para estructurar las secciones de nuestro proyecto, incluyendo un header con navegación y un footer, permitiendo que el contenido cambie sin perder la estructura base.
      En este caso, el layout se encargó de gestionar las rutas como "Inicio", "Acerca de", y "Experiencias" dentro de un mismo diseño.
    </p>
  </div>
</template>

<style scoped>
.welcome-container {
  text-align: center;
  margin-top: 20px;
  padding: 20px;
  font-family: 'Roboto', sans-serif;
  background-color: #F5F7FA;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #1A73E8;
  font-size: 32px;
  margin-bottom: 10px;
}

h2 {
  color: #333;
  font-size: 24px;
  margin-bottom: 20px;
}

p {
  font-size: 16px;
  line-height: 1.6;
  margin: 0 auto;
  max-width: 800px;
  color: #555;
}
</style>