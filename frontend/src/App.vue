<template>
  <div id="main">
    <div class="info">
      <h1 class="title">
        <pre>&lt;zap-slideout&gt;</pre>
      </h1>
      <p class="description">
        Give it a jolt. Click <strong>Open</strong> at the top.
      </p>
    </div>
    <div>
      <sidebar></sidebar>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
/* main css, body, etc */
body {
  font-family: 'Helvetica Neue', Arial, sans-serif;
  color: #fff;
  background-color: #2c3e50;
}

strong {
  font-weight: 600;
}

.info {
  position: absolute;
  top: 50%;
  right: 50%;
  transform: translateX(50%);
  text-align: center;

}

.title {
  font-size: 24px;
  font-weight: 600;
}

.description {
  margin-top: 20px;
}

/* responsive grid */

* {
  box-sizing: border-box;
}
</style>

<script>
import Sidebar from './components/Sidebar'

export default {
  components: {
    'sidebar': Sidebar
  },
  name: 'app'
}

</script>
