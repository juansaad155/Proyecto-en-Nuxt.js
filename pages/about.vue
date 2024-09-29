<template>
  <div class="about-container">
    <h1>Acerca de Nosotros</h1>
    <div class="authors">
      <div class="author" v-for="author in authors" :key="author.name">
        <div class="author-info">
          <a :href="author.instagram" target="_blank">
            <img :src="author.photo" :alt="author.name" class="author-photo" />
          </a>
          <div class="author-details">
            <h2>{{ author.name }}</h2>
            <p><strong>Teléfono:</strong> {{ author.phone }}</p>
            <p><strong>Correo:</strong> <a :href="'mailto:' + author.email">{{ author.email }}</a></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      authors: [
        {
          name: 'Juan Saad',
          photo: '/images/juan.jpg',
          instagram: 'https://www.instagram.com/juanfluxo_/',
          phone: '3115259315',
          email: 'juandsaadperez0@gmail.com'
        },
        {
          name: 'Yuliana Otero',
          photo: '/images/yuliana.jpg',
          instagram: 'https://www.instagram.com/yuliana_ackerman26/',
          phone: '3002695093',
          email: 'yujulian04@gmail.com'
        },
        {
          name: 'Luis Gómez',
          photo: '/images/luis.jpg',
          instagram: 'https://www.instagram.com/luisgo_29/',
          phone: '3044425018',
          email: 'gcluisdavid29@gmail.com'
        }
      ]
    };
  }
};
</script>

<style scoped>
.about-container {
  text-align: center;
  padding: 40px 20px;
  background-color: #F5F7FA;
}

.authors {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-top: 40px;
}

.author {
  margin: 20px;
  transition: transform 0.3s ease;
}

.author-info {
  border: 3px solid #1A73E8;
  border-radius: 15px;
  padding: 20px;
  width: 300px;
  background-color: #fff;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); 
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.author-info:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15); 
}

.author-photo {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.author-details {
  margin-top: 15px;
  text-align: center;
}

.author-details h2 {
  font-size: 20px;
  color: #333;
  margin-bottom: 10px;
}

.author-details p {
  margin: 5px 0;
  font-size: 16px;
  color: #555;
}

.author-details a {
  color: #1A73E8;
  text-decoration: none;
  font-weight: bold;
}

.author-details a:hover {
  text-decoration: underline;
}
</style>