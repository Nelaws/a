<template>
<div>
  <div v-for="comment in comments">
    {{comment.body}}
  </div>
</div>
</template>

<script>
import axios from "axios";

export default {
  name: "CommentPost",
  props:[
    'comments'
  ],
  data() {
    return {
      PostComment: {
        body: undefined,
        created_at: undefined,
        id: undefined,
        product_id: undefined,
        title: undefined,
        updated_at: undefined,
        user_id: undefined
      }
    }
  },
  async mounted() {

  }
}
</script>

<style scoped>

</style>