<template>
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
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="css">
@import '../static/style.css';
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
