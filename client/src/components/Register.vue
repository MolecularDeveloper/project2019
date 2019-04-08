/* eslint-disable */
<template>
  <div class="hello">
    <h1>User Login</h1>
    <input type="email"
           name="email"
           v-model="email"
           placeholder="email" />
    <input type="password"
           name="password"
           v-model="password"
           placeholder="password" />
  <button
    @click="register()">
    Register
  </button>

  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 li{ list-style-type: none;}
</style>
