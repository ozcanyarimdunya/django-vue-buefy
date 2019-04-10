<template>
  <div>
    <app-header v-if="isAuthenticated"></app-header>
    <main class="bd-main">
      <router-view></router-view>
    </main>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import {mapGetters} from "vuex";
  import AppHeader from "./components/AppHeader";
  import AppFooter from "./components/AppFooter";

  export default {
    name: 'app',
    components: {
      AppFooter,
      AppHeader,
    },
    computed: mapGetters('auth', [
      'isAuthenticated',
    ]),
  };
</script>

<style>
  html {
    font-family: "Roboto", "Lucida Grande", "DejaVu Sans", "Bitstream Vera Sans", Verdana, Arial, sans-serif
  }

  .bd-main {
    padding: 1rem 3rem;
  }
</style>
