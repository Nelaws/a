<template>
  <div>
      <h2>Войдите в аккаунт</h2>
      <form @submit.prevent="login">
        <input type="text" v-model="users.name" placeholder="Введите имя">
        <input type="email" v-model="users.email" placeholder="Введите почту">
        <input type="password" v-model="users.password" placeholder="Введите пароль">
        <button type="submit">Войти</button>
      </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "SignInView",
 data() {
    return {
      users: [
          {
            name: null,
            email: null,
            password: null
          }
      ]
    }
 },
  // methods: {
  //   login: function () {
  //     let name = this.users.name
  //     let email = this.users.email
  //     let password = this.users.password
  //     this.$store.dispatch('login', {name, email, password })
  //         .then(() => this.$router.push('/'))
  //         .catch(err => console.log(err))
  //   }
  // },
  async mounted() {
    await axios.post('http://127.0.0.1:8000/api/login')
        .then(response => (this.users = response));
  }
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
}
form input {
  height: 20px;
  margin: 5px;
}
form button {
  width: 177px;
}
</style>