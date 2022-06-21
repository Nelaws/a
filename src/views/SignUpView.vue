<template>
  <div>
      <h2>Регистрация аккаунта</h2>
      <form v-if="!isName" v-on:submit="isName=true">
        <input type="text" v-model="name" placeholder="Введите имя">
        <input type="email" v-model="email" placeholder="Введите почту">
        <input type="password" v-model="password" placeholder="Введите пароль">
        <button type="submit">Регистрация</button>
      </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "SignInView",
  data() {
    return {
      name: '',
      email: '',
      password: '',
      isName: false
    }
  },
  async mounted() {
    await axios.post('http://127.0.0.1:8000/api/register')
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