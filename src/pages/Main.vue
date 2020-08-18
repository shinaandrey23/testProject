
<template>
  <Layout>
    <loginForm
      v-if="this.userInfo.isLogin === false"
    />
    <div v-else>
      <p>User: {{ user.username }}</p>
    </div>
  </Layout>
</template>

<script>
import axios from 'axios'
import loginForm from "../components/loginForm";

export default {
  components: {loginForm},
  metaInfo: {
    title: 'Login'
  },
  data: {
    user: loginForm.userInfo.user
  }
}
</script>

