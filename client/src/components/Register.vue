<template>
  <div class="register">
  <h1>Register</h1>
  <input
    type="text"
    name="email"
    v-model="email"
    placeholder="email"
    />
    <br>
  <input
    type="password"
    name="password"
    v-model="password"
    placeholder="password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '../services/AuthenticationService'
export default {
  name: 'Register',
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  watch: {
    email (value) {
      console.log('email has changed', value)
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log('hello 2', response.data)
    }
  }
}
</script>

<style scoped>
</style>
