<template>
  <section class="section">
    <div class="columns is-mobile">
      <div class="column"></div>
      <div class="column">
        <div class="logo">
          <p>LOGIN</p>
        </div>
        <hr>

        <form @submit.prevent="onLogin">
          <b-field label="Username">
            <b-input v-model="user.username" icon-pack="fas" icon="user"></b-input>
          </b-field>

          <b-field label="Password">
            <b-input v-model="user.password" type="password" icon-pack="fas" icon="key" password-reveal></b-input>
          </b-field>
          <b-field>
            <div class="control">
              <b-loading :is-full-page="true" :active.sync="authenticating"></b-loading>
              <button type="submit" class="button is-info btn-login" v-model="authenticating">
                Login
              </button>
            </div>
          </b-field>
        </form>
      </div>
      <div class="column"></div>
    </div>
  </section>
</template>

<script>
  import {mapState, mapActions} from 'vuex';

  export default {
    name: "Login",
    components: {},
    data() {
      return {
        user: {
          username: null,
          password: null
        }
      }
    },
    computed: {
      ...mapState('auth', ['authenticating', 'error', 'token']),
    },
    methods: {
      ...mapActions('auth', ['login']),

      onLogin() {
        if (this.user.username && this.user.password) {

          const user = this.user;
          this.login(user)
            .then(() => {
              if (!this.error) {
                this.$router.push('/')
              } else {
                this.$snackbar.open(`Invalid credentials!`)
              }
            });
        }
      },
    },
  }
</script>

<style scoped>
  .btn-login {
    width: 100%;
    margin: 1rem 0;
  }

  .logo {
    font-size: 32px;
    text-align: center;
  }
</style>