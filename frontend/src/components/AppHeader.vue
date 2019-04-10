<template>
  <nav class="navbar has-shadow is-spaced" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="#">
        <img src="@/assets/logo.png" width="100" height="28" alt="Logo">
      </a>

      <a role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false"
         data-target="navbarBasic">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasic" class="navbar-menu">
      <div class="navbar-start">
        <router-link to="/" class="navbar-item is-active">Home</router-link>
        <router-link to="/about" class="navbar-item">About</router-link>
      </div>
      <div class="navbar-end">
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">Account</a>
          <div class="navbar-dropdown">
            <router-link to="/profile" class="navbar-item">Profile</router-link>
            <router-link to="/admin" class="navbar-item">Admin</router-link>
            <hr class="navbar-divider">
            <router-link to="/logout" class="navbar-item">Logout</router-link>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
  export default {
    name: "AppHeader",
    methods: {},
  }
</script>

<style scoped>

</style>