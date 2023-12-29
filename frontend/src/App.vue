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
import Sidebar from './components/Sidebar'

export default {
  components: {
    'sidebar': Sidebar
  },
  name: 'app',
  data() {
    this.handleAuthentication()
    this.authenticated = false

    return {
      authenticated: false,
      message: ''
    }
  },

  methods: {
    login() {
    },
    handleAuthentication() {
    },
    logout() {
    },
    privateMessage() {
      this.messgae = 'private message'
    }
  }
}

</script>
