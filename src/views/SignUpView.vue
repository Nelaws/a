<template>
  <div>
    <form>
      <h2>Регистрация аккаунта</h2>
      <input type="text" placeholder="Логин">
      <input type="password" placeholder="Пароль">
      <button type="submit">Войти</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "SignInView"
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 300px;
}
form input {
  height: 20px;
  margin: 5px;
}
form button {
  width: 177px;
}
</style>