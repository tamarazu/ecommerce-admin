<template>
  <div id="app">
    <NavbarAdmin></NavbarAdmin>
    <router-view />
  </div>
</template>

<script>

import NavbarAdmin from './components/NavbarAdmin'

export default {
  name: 'NavbarLogin',
  components: {
    NavbarAdmin
  },
  created () {
    if (localStorage.access_token) {
      this.$router.push('/')
    } else {
      this.$router.push('/login')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
