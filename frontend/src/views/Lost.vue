<template>
  <section>
    <div class="columns is-mobile">
      <div class="column"></div>
      <div class="column forbidden">
        <b-icon pack="fas" icon="ban" size="is-large" type="is-danger" custom-size="fa-5x"></b-icon>
        <h2>Page Not Found!</h2>
        <router-link to="/" class="to-home">
          <b-icon pack="fas" icon="home" size="is-small"></b-icon>
          Take me home.
        </router-link>
      </div>
      <div class="column"></div>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'lost',
  };
</script>
<style scoped>

  .forbidden {
    text-align: center;
    margin: 5rem 0;
  }

  .forbidden h2 {
    margin-top: 2rem;
    color: #CC0011;
    font-size: 20px;
  }

  .to-home {
    font-size: 14px;
    margin-top: 2rem;
  }
</style>