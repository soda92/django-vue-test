<template>
  <div>
    <button class="btn btn-primary btn-margin" v-if="!authenticated" @click="login()">
      Log In
    </button>
    <button class="btn btn-primary btn-margin" v-if="authenticated" @click="privateMessage()">
      Call Private
    </button>

    <button class="btn btn-primary btn-margin" v-if="authenticated" @click="logout()">
      Log Out
    </button>
    {{ message }}
    <br>
    <div id="main">
      <div class="info">
        <h1 class="title">
          <pre>&lt;zap-slideout&gt;</pre>
        </h1>
        <p class="description">Give it a jolt. Click <strong>Open</strong> at the top.</p>
      </div>
      <div>
        <sidebar></sidebar>
      </div>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  color: #42b983;
}
</style>

<script>
import AuthService from './auth/AuthService'
import Sidebar from './components/Sidebar'
import axios from 'axios'

const API_URL = 'http://localhost:8000'
const auth = new AuthService()

export default {
  components: {
    'sidebar': Sidebar
  },
  name: 'app',
  data() {
    this.handleAuthentication()
    this.authenticated = false

    auth.authNotifier.on('authChange', authState => {
      this.authenticated = authState.authenticated
    })

    return {
      authenticated: false,
      message: ''
    }
  },

  methods: {
    login() {
      auth.login()
    },
    handleAuthentication() {
      auth.handleAuthentication()
    },
    logout() {
      auth.logout()
    },
    privateMessage() {
      const url = `${API_URL}/api/private`
      return axios.get(
        url,
        {
          headers:
          {
            Authorization: `Bearer ${auth.getAuthToken()}`
          }
        }
      ).then(
        (response) => {
          console.log(response.data)
          this.messgae = response.data || ''
        }
      )
    }
  }
}

</script>
