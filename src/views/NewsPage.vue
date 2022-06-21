<template>
  <div class="Posts">
    <h3>{{post.name}}</h3>
    <span>{{post.description}}</span>
    <h4>Комментарии:</h4>
    <CommentPost :comments="post.lists"/>
  </div>
</template>

<script>
import axios from "axios";
import CommentPost from "@/views/CommentPost";

export default {
  name: "NewsPage",
  components: {CommentPost},
  data() {
    return {
      post: {
        created_at: undefined,
        description: undefined,
        id: undefined,
        name: undefined,
        updated_at: undefined
      },
      comments: [
        {
          comment: null
        }
      ]
    };
  },
  async mounted() {
    await axios.get(`http://127.0.0.1:8000/api/posts/${this.$route.params.id}`)
        .then(response => (this.post = response.data.data));
  }
}
</script>

<style scoped>
.Posts {
  display: flex;
  flex-direction: column;
}
</style>