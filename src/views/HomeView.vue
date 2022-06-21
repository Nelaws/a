<template>
  <div>
    <div v-for="post in posts" class="home">
      <span @click="goTo(post.id)">
        {{ post.name }}
      </span>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'HomeView',
  data() {
    return {
      posts: [
        {
          name: null,
          description: null,
          created_at: null,
          id: null
        }
      ]
    };
  },
  async mounted() {
    await axios.get('http://127.0.0.1:8000/api/posts')
        .then(response => (this.posts = response.data));

  },
  methods: {
    goTo(id) {
      this.$router.push({
        path: `/news_page/${id}`
      })
    }
  }
}
</script>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.home span {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  font-size: 20px;
  margin-bottom: 20px;
  width: auto;
}
</style>
