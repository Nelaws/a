<template>
  <div id="app">
    <div class="headerPage">
        <div class="NameSite">
          <router-link to="/"><h2>NOVOSTNOI SAIT</h2></router-link>
        </div>
        <nav class="authPage">
          <router-link to="/sign_in">Sign in</router-link> |
          <router-link to="sign_up">Sign up</router-link>
        </nav>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
.headerPage {
  display: flex;
  justify-content: space-between;
}
.authPage {
  display: flex;
  align-items: center;
}
.authPage a {
  text-decoration: none;
  color: black;
}
.authPage a {
  text-decoration: none;
  color: black;
}
.NameSite a {
  text-decoration: none;
  color: black;
}
</style>
