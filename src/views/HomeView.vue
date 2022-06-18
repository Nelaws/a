<template>
  <div>
    <div
        v-for="post in posts" class="home">
      <router-link to="/news_page">{{post.name}}
      </router-link>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'HomeView',
  data () {
    return {
      posts: [
        {
          name: null,
          description: null,
          created_at: null
        }
      ]
    };
  },
  async mounted() {
    await axios.get('http://127.0.0.1:8000/api/posts')
        .then(response => (this.posts = response.data));

  }
}
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.home a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  font-size: 25px;
  margin-bottom: 20px;
  width: 200px;
}
</style>
