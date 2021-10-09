<template>
  <router-view />
</template>

<style lang="scss">
.flex {
  display: flex;
}

.flex-column {
  flex-direction: column;
}

.btn {
  background: none;
  border: none;
  border-radius: 28px;
  font-size: 1rem;
  padding: 15px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
  padding: 0;

}
html, body, #app {
  height: 100%;
  width: 100%;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
