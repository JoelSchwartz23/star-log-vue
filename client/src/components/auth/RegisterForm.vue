<template>
  <div>
    <form @submit.prevent="register">
      <input type="text" v-model="creds.name">
      <input type="text" v-model="creds.email">
      <input type="password" v-model="creds.password">
      <button type="submit">Register</button>
      <button type="reset">Clear</button>
    </form>
  </div>
</template>


<script>
  export default {
    name: 'RegisterForm',
    data() {
      return {
        creds: {
          name: '',
          email: '',
          password: ''
        }
      }
    },
    methods: {
      register() {
        this.$store.dispatch('register', this.creds)
      }
    }
  }
</script>