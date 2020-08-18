<template>
  <Layout>
    <loginForm
      v-if="!isLogin"
    />
    <div v-else>
      <p>User: {{ user.username }}</p>
    </div>
  </Layout>
</template>

<script>
import axios from 'axios'
import loginForm from "../components/loginForm"

export default {
  components: {loginForm},
  metaInfo: {
    title: 'Login'
  },
  data: function () {
    return {
      isLogin: loginForm.isLogin,
      user: loginForm.user
    }
  }
}
</script>

