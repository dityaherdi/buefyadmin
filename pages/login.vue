<template>
  <div class="columns is-vcentered">
    <div class="login column is-4">
      <section class="section">
        <div class="has-text-centered">
          <img class="login-logo" src="/img/logo_r_resumme.png" />
        </div>

        <form @submit.prevent="login()">
          <b-field label="Username">
            <b-input
              maxlength="20"
              v-model="credentials.username"
              icon="account"
            ></b-input>
          </b-field>

          <b-field label="Password">
            <b-input
              type="password"
              v-model="credentials.password"
              password-reveal
              icon="key"
            >
            </b-input>
          </b-field>
          <div class="has-text-centered">
            <!-- <a class="button is-vcentered is-primary is-outlined">Login</a> -->
            <!-- <nuxt-link
              to="/"
              tag="a"
              class="button is-vcentered is-primary is-outlined"
              >Login</nuxt-link
            > -->
            <b-button
              tag="input"
              type="is-primary"
              native-type="submit"
              value="Login"
            />
          </div>
        </form>

        <div class="has-text-centered">
          <!-- <a href="#"> Don't you have an account? Sign up now!</a> -->
        </div>
      </section>
    </div>
    <div id="particles-js" class="interactive-bg column is-8"></div>
  </div>
</template>

<script>
export default {
  layout: 'auth',
  data: () => ({
    credentials: {
      username: '',
      password: '',
    },
  }),
  methods: {
    login() {
      console.log(this.credentials)
    },
  },
}
</script>

<style scoped>
.interactive-bg {
  height: 100vh;
  background-color: #00d1b2;
  -webkit-box-shadow: inset 24px 4px 64px -24px rgba(71, 71, 71, 1);
  -moz-box-shadow: inset 24px 4px 64px -24px rgba(71, 71, 71, 1);
  box-shadow: inset 24px 4px 64px -24px rgba(71, 71, 71, 1);
  padding: 0px;
}
@media (max-width: 769px) {
  .interactive-bg {
    display: none;
  }
}

.input {
  border-radius: 50px;
}

.button {
  margin-top: 20px;
  margin-bottom: 20px;
  min-width: 150px;
}

.login-logo {
  margin: 0 auto;
  margin-bottom: 50px;
  max-height: 100px;
}

.columns {
  margin: 0px;
}
</style>