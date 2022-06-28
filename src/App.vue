<template>
  <div class="wrapper123">
    <nav class="nav_bar123">
      <div>Аналитика</div>
      <router-link to="/">Главная</router-link>
      <router-link to="/projects">Проекты</router-link>
      <router-link to="/users">Пользователи</router-link>
      <router-link to="/settings">Настройки</router-link>
    </nav>
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
}
.wrapper123 {
  height: 100vh;
  display: flex;
  flex-direction: row;
}
.nav_bar123 {
  width: 200px;
  height: 100%;
  display: flex;
  gap: 15px;
  flex-direction: column;
  justify-content: start;
  align-items: start;
  padding-left: 10px;
  padding-top: 20px;
  background-color: rgba(188, 188, 188, 0.678);
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
