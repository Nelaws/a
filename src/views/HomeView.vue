<template>
  <nav class="home">
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
    <router-link to="/news_page">wwewewe</router-link>
  </nav>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
}
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  font-size: 25px;
  margin-bottom: 20px;
  width: 200px;
}
</style>
