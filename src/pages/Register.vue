<template>
  <Layout>
    <form @submit.prevent="reg" v-if="!response.data.user.id">
      <label for="login">Login:</label><br>
      <input type="text" id="login" v-model="username"><br>
      <label for="email">Email:</label><br>
      <input type="email" id="email" v-model="email"><br>
      <label for="password">Password:</label><br>
      <input type="password" id="password" v-model="password"><br>
      <label>Role:</label>
      <input type="radio" id="Farmer" name="role" value="Farmer">
      <label for="Farmer">Farmer</label>
      <input type="radio" id="Beekeeper" name="role" value="Beekeeper">
      <label for="Beekeeper">Beekeeper</label><br><hr>
      <button type="submit">Register</button>
    </form>
    <div v-else>Auth</div>
  </Layout>

</template>

<script>
import axios from "axios";

export default {
name: "Register.vue",
data() {
  return {
    username: '',
    email: '',
    password: '',
    role: ''
  }
},
methods: {
  reg() {
    axios.post('http://localhost:1337/auth/local/register', {
      username: this.username,
      email: this.email,
      password: this.password,
    }).then(response => {
      // Handle success.
      console.log('Well done!')
      console.log('User profile', response.data.user)
      console.log('User token', response.data.jwt)
    }).catch(error => {
      // Handle error.
      console.log('An error occurred:', error.response)
    })
  }
}
}
</script>

<style scoped>

</style>