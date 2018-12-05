<template>
  <div>
    <form @submit.prevent="login">
      <input type="text" v-model="creds.email">
      <input type="password" v-model="creds.password">
      <button type="submit">Login</button>
      <button type="reset">Clear</button>
    </form>
  </div>
</template>


<script>
  export default {
    name: 'LoginForm',
    data() {
      return {
        creds: {
          email: '',
          password: ''
        }
      }
    },
    methods: {
      login() {
        this.$store.dispatch('login', this.creds)
      }
    }
  }
</script>